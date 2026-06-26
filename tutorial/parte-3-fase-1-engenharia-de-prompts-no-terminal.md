# Parte 3 — Fase 1: Engenharia de Prompts no Terminal

## Objetivo
Passar contexto certo do monorepo para obter respostas úteis e consistentes.

## Contexto do projeto
- API NestJS em `apps/api`
- Web Next.js em `apps/web`
- Persistência PostgreSQL em `packages/db`

## 1) Como passar arquivos locais como contexto
Estratégia recomendada:
- Incluir arquivos de contrato (DTOs, interfaces, schema)
- Incluir arquivo alvo e dependências diretas
- Evitar contexto excessivo que polui o resultado

## 2) Estrutura de prompt eficiente
Modelo de estrutura:
1. Papel da IA (ex.: “atue como engenheiro fullstack sênior”)
2. Objetivo exato (o que mudar)
3. Restrições técnicas (stack, padrões e segurança)
4. Escopo de arquivos
5. Critérios de aceite

## Exemplo de tarefa da fase
Solicitar endpoint NestJS para cadastro e tela Next.js correspondente, usando a mesma modelagem do PostgreSQL.

## Critérios de qualidade
- Código claro e legível
- Sem quebra de padrão do monorepo
- Sem exposição de dados sensíveis
