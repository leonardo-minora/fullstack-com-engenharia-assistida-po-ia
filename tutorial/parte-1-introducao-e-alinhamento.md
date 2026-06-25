# Parte 1 — Introdução e Alinhamento (15 min)

## Objetivo
Entender como usar LLMs no ciclo de desenvolvimento com foco em produtividade via terminal.

## Exemplo único da aula (fullstack monorepo)
Neste tutorial, todo o conteúdo usa o mesmo projeto:
- `apps/api`: NestJS (API)
- `apps/web`: Next.js (frontend)
- `packages/db`: camada de persistência PostgreSQL (migrations, schema e acesso a dados)

## 1) O ecossistema de IA no SDLC
Use IA para acelerar etapas, sem abrir mão de validação humana:
- Descoberta e refinamento de requisitos
- Geração e revisão inicial de código
- Testes automatizados
- Documentação
- Apoio em revisão de PRs

## 2) Por que CLI
Benefícios práticos:
- Fluxo rápido sem sair do terminal
- Fácil automação com scripts
- Integração com Git, linters e testes

## 3) Gemini CLI: capacidades e limites
### Capacidades
- Gerar, explicar e refatorar código
- Sugerir testes
- Produzir documentação técnica

### Limitações
- Pode alucinar APIs inexistentes
- Pode inferir arquitetura errada sem contexto
- Pode sugerir código inseguro se o prompt for fraco

## Resultado esperado da Parte 1
Você entende **onde** a IA ajuda no SDLC e **como** posicionar o Gemini CLI no fluxo diário de engenharia.
