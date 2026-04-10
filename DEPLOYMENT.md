# Guia de Deployment - FastInBox

## Arquitetura de Deployment

- **Frontend**: Vercel (Next.js 15)
- **Backend**: Render (NestJS 11)
- **Banco de Dados**: Neon (PostgreSQL)
- **Cache e filas leves**: Redis gerenciado

## Premissas

- esta estrutura segue o padrao de documentacao usado como referencia para o projeto
- a arquitetura abaixo e uma base recomendada para o contexto atual do FastInBox
- `front` e `back` permanecem em repositorios separados na organizacao `FastInBox-Repo`

## Pre-requisitos

1. Conta no [Vercel](https://vercel.com)
2. Conta no [Render](https://render.com)
3. Projeto PostgreSQL configurado no [Neon](https://neon.tech)
4. Instancia Redis gerenciada configurada
5. Repositorios `front` e `back` conectados ao GitHub

## 1. Deploy do Backend no Render

### Configuracao Manual

1. Acesse o [Render Dashboard](https://dashboard.render.com)
2. Clique em `New` > `Web Service`
3. Conecte o repositorio `FastInBox-Repo/back`
4. Configure:
   - **Name**: `fastinbox-api`
   - **Branch**: `main`
   - **Root Directory**: `back`
   - **Runtime**: `Node`
   - **Build Command**: `npm install && npm run build`
   - **Start Command**: `npm run start:prod`

### Variaveis de Ambiente

No dashboard do Render, adicione:

```env
PORT=4001
NODE_ENV=production
FRONTEND_URL=https://app.fastinbox.com
BACKEND_URL=https://api.fastinbox.com
DATABASE_URL=postgresql://user:password@ep-xxx.us-east-2.aws.neon.tech/neondb?sslmode=require
REDIS_HOST=your-redis-host
REDIS_PORT=6379
REDIS_PASSWORD=your-redis-password
REDIS_DB=0
```

### Observacoes

- o Render injeta a porta de execucao em ambiente gerenciado; a aplicacao deve respeitar `process.env.PORT`
- use um health check HTTP assim que a API tiver rota dedicada para observabilidade
- o deploy automatico pode ficar vinculado a cada push para a branch principal

## 2. Deploy do Frontend no Vercel

### Via Dashboard

1. Acesse o [Vercel Dashboard](https://vercel.com/dashboard)
2. Clique em `Add New` > `Project`
3. Importe o repositorio `FastInBox-Repo/front`
4. Configure:
   - **Framework Preset**: `Next.js`
   - **Root Directory**: `front`
   - **Install Command**: `npm install`
   - **Build Command**: `npm run build`

### Variaveis de Ambiente

No projeto do Vercel, configure:

```env
NEXT_PUBLIC_API_URL=https://api.fastinbox.com
NEXT_PUBLIC_SITE_URL=https://app.fastinbox.com
INTERNAL_API_URL=https://api.fastinbox.com
```

### Observacoes

- o frontend atual usa `Next.js 15` com App Router
- use dominio proprio quando a camada institucional estiver pronta
- previews de pull request podem ser habilitados automaticamente pelo fluxo Git baseado em branch

## 3. Banco de Dados e Redis

### PostgreSQL

1. Crie um projeto no Neon
2. Gere a connection string com SSL habilitado
3. Atualize `DATABASE_URL` no backend
4. Execute as migrations quando essa camada estiver definida no repositorio `back`

### Redis

1. Crie uma instancia Redis gerenciada
2. Copie host, porta, senha e database
3. Atualize as variaveis `REDIS_HOST`, `REDIS_PORT`, `REDIS_PASSWORD` e `REDIS_DB`

## 4. Fluxo Sugerido de Publicacao

1. Atualizar a branch principal de `back`
2. Validar o deploy automatico da API no Render
3. Atualizar a branch principal de `front`
4. Validar o deploy automatico do frontend no Vercel
5. Executar verificacoes funcionais do fluxo nutricionista -> paciente -> pagamento -> cozinha

## 5. Testando o Ambiente Publicado

### Backend

```bash
curl https://api.fastinbox.com
```

### Frontend

Acesse: `https://app.fastinbox.com`

## Troubleshooting

### Backend nao responde

- verificar logs no Render Dashboard
- confirmar `PORT`, `DATABASE_URL` e credenciais Redis
- validar se a aplicacao esta bindando em `0.0.0.0`

### Frontend nao encontra a API

- verificar `NEXT_PUBLIC_API_URL`
- confirmar CORS no backend
- validar se a URL publica da API esta acessivel

### Erro de conexao com banco

- verificar `DATABASE_URL`
- confirmar se o banco aceita conexoes externas
- validar credenciais, SSL e regras de rede

## CI/CD

- push para a branch principal dos repositorios aplica deploy automatico conforme a configuracao de cada plataforma
- pull requests podem ser usados para revisar mudancas antes de promover o deploy
- este repositorio `.github` possui CI propria para validar a documentacao e a estrutura de GitHub
