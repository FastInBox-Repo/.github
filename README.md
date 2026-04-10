<div align="center">

# FastInBox

**Repositorio de perfil e padroes compartilhados da organizacao FastInBox**

[![Next.js](https://img.shields.io/badge/Next.js-15.5-000000?logo=nextdotjs&logoColor=white)](https://nextjs.org/)
[![React](https://img.shields.io/badge/React-19.1-61DAFB?logo=react&logoColor=black)](https://react.dev/)
[![NestJS](https://img.shields.io/badge/NestJS-11.0-E0234E?logo=nestjs&logoColor=white)](https://nestjs.com/)
[![PostgreSQL](https://img.shields.io/badge/PostgreSQL-17-4169E1?logo=postgresql&logoColor=white)](https://www.postgresql.org/)
[![Redis](https://img.shields.io/badge/Redis-Cache-DC382D?logo=redis&logoColor=white)](https://redis.io/)
[![Tailwind CSS](https://img.shields.io/badge/Tailwind-4.0-38B2AC?logo=tailwind-css&logoColor=white)](https://tailwindcss.com/)

Este repositorio centraliza o perfil publico da organizacao, a documentacao de alto nivel e os arquivos compartilhados da camada GitHub.

Site oficial de documentacao (GitHub Pages):

- [https://fastinbox-repo.github.io/docs/](https://fastinbox-repo.github.io/docs/)

</div>

---

## Indice

- [Visao Geral](#visao-geral)
- [Repositorios Principais](#repositorios-principais)
- [Estrutura do GitHub](#estrutura-do-github)
- [Governanca de Colaboracao](#governanca-de-colaboracao)
- [Deploy](#deploy)
- [Perfil Publico](#perfil-publico)

---

## Visao Geral

FastInBox e uma plataforma white label para operacao de marmitas personalizadas, conectando clinicas, nutricionistas, pacientes, cozinhas parceiras e administracao em um fluxo unico.

Este repositorio `.github` existe para padronizar a apresentacao da organizacao no GitHub e concentrar os arquivos que orientam a camada institucional e operacional do projeto.

---

## Repositorios Principais

- [`FastInBox-Repo/front`](https://github.com/FastInBox-Repo/front): frontend web em Next.js para as jornadas de nutricionista, paciente, cozinha e administracao
- [`FastInBox-Repo/back`](https://github.com/FastInBox-Repo/back): backend em NestJS responsavel por autenticacao, regras de negocio, pedidos e operacao
- [`FastInBox-Repo/.github`](https://github.com/FastInBox-Repo/.github): perfil publico da organizacao, documentacao compartilhada e padroes GitHub

---

## Estrutura do GitHub

```text
FastInBox-Repo/
├── .github/
│   ├── README.md                 # Repositorio de perfil e padroes compartilhados
│   ├── DEPLOYMENT.md             # Guia de deployment do ecossistema FastInBox
│   ├── CONTRIBUTING.md           # Guia de contribuicao da organizacao
│   ├── CODE_OF_CONDUCT.md        # Codigo de conduta de colaboracao
│   ├── SECURITY.md               # Politica de seguranca e reportes
│   ├── profile/
│   │   └── README.md             # Perfil publico exibido na pagina da organizacao
│   └── .github/
│       ├── pull_request_template.md
│       ├── ISSUE_TEMPLATE/
│       │   ├── bug_report.yml
│       │   ├── feature_request.yml
│       │   ├── technical_task.yml
│       │   └── config.yml
│       └── workflows/
│           └── ci.yml            # CI da documentacao e estrutura GitHub
├── front/                        # Aplicacao web em Next.js 15
└── back/                         # API NestJS 11
```

---

## Governanca de Colaboracao

Arquivos de padronizacao foram adicionados para manter trilha profissional de trabalho entre repositorios:

- `CONTRIBUTING.md`: fluxo de contribuicao e convencoes
- `CODE_OF_CONDUCT.md`: diretrizes de convivencia tecnica
- `SECURITY.md`: politica de reporte de vulnerabilidades
- templates de issue e pull request em `.github/`

---

## Deploy

O guia de deployment desta organizacao esta em [`DEPLOYMENT.md`](./DEPLOYMENT.md). Ele documenta a arquitetura sugerida para frontend, backend, banco relacional e cache, alinhada ao contexto atual do FastInBox.

---

## Perfil Publico

O conteudo exibido na pagina principal da organizacao fica em [`profile/README.md`](./profile/README.md). Esse arquivo segue o mesmo padrao de apresentacao adotado como referencia, mas adaptado ao contexto do FastInBox.
