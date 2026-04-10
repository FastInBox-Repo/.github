<div align="center">

# FastInBox

**Plataforma white label para operacao de marmitas personalizadas**

[![Next.js](https://img.shields.io/badge/Next.js-15.5-000000?logo=nextdotjs&logoColor=white)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.1-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![NestJS](https://img.shields.io/badge/NestJS-11.0-E0234E?logo=nestjs&logoColor=white)](https://nestjs.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-17-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Redis](https://img.shields.io/badge/Redis-Cache-DC382D?logo=redis&logoColor=white)](https://redis.io/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.0-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

Documentacao principal da organizacao:

- [Site oficial (GitHub Pages)](https://fastinbox-repo.github.io/docs/)

- [Frontend](https://github.com/FastInBox-Repo/front)
- [Backend](https://github.com/FastInBox-Repo/back)
- [Guia de Deployment](https://github.com/FastInBox-Repo/.github/blob/main/DEPLOYMENT.md)

</div>

---

## Indice

- [Visao Geral](#visao-geral)
- [Stack Tecnologico](#stack-tecnologico)
- [Estrutura da Organizacao](#estrutura-da-organizacao)
- [Fluxo Operacional](#fluxo-operacional)
- [Repositorios Principais](#repositorios-principais)
- [Deploy](#deploy)

---

## Visao Geral

FastInBox e uma plataforma full-stack para venda e operacao de marmitas personalizadas em modelo white label, permitindo:

- **Nutricionistas e clinicas**: cadastrar pacientes, montar pedidos e operar com sua propria marca
- **Pacientes**: revisar, confirmar, pagar e acompanhar pedidos com uma jornada clara
- **Cozinhas parceiras**: receber pedidos pagos, produzir e atualizar o status operacional
- **Administracao**: monitorar usuarios, pedidos, pagamentos, comissoes e governanca da operacao

---

## Stack Tecnologico

### Frontend

- **Next.js 15.5** + **React 19.1**
- **TypeScript**
- **Tailwind CSS 4**
- **App Router**

### Backend

- **NestJS 11**
- **TypeScript 5.7**
- **PostgreSQL 17**
- **Redis**

### Organizacao

- **GitHub Organization** com separacao por repositorio
- **Repositorio `.github`** para perfil publico e padroes compartilhados

---

## Estrutura da Organizacao

```text
FastInBox-Repo/
├── .github/
│   ├── README.md                 # Repositorio de perfil e padroes GitHub
│   ├── DEPLOYMENT.md             # Guia de deployment do ecossistema
│   ├── profile/
│   │   └── README.md             # Perfil publico da organizacao
│   └── .github/
│       └── workflows/
│           └── ci.yml            # CI da documentacao GitHub
├── front/
│   ├── app/                      # Rotas com App Router
│   ├── components/               # Providers e componentes compartilhados
│   └── src/figma-app/            # Interface e paginas do MVP
└── back/
    ├── src/                      # API e regras de negocio
    ├── test/                     # Testes automatizados
    └── docker-compose.yml        # Infra local com PostgreSQL e Redis
```

---

## Fluxo Operacional

1. O nutricionista cadastra o paciente ou inicia um pedido
2. O pedido e configurado com itens, valores e contexto white label
3. O sistema disponibiliza o pedido para revisao do paciente
4. O paciente confirma e segue para pagamento
5. O pedido pago entra na fila operacional da cozinha
6. A cozinha atualiza producao e entrega
7. A administracao acompanha toda a operacao em ambiente centralizado

---

## Repositorios Principais

- [`FastInBox-Repo/front`](https://github.com/FastInBox-Repo/front): aplicacao web em Next.js para as jornadas do MVP
- [`FastInBox-Repo/back`](https://github.com/FastInBox-Repo/back): API em NestJS para autenticacao, dados e regras operacionais
- [`FastInBox-Repo/.github`](https://github.com/FastInBox-Repo/.github): perfil da organizacao, documentacao compartilhada e padroes GitHub

---

## Deploy

O guia de deployment da organizacao esta em [`DEPLOYMENT.md`](https://github.com/FastInBox-Repo/.github/blob/main/DEPLOYMENT.md), cobrindo frontend, backend, banco relacional e camada Redis.

Para a apresentacao academica, o link publico oficial da documentacao e:

- [https://fastinbox-repo.github.io/docs/](https://fastinbox-repo.github.io/docs/)
