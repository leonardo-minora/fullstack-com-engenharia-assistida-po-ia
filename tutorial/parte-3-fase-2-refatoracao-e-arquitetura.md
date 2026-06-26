# Parte 3 — Fase 2: Refatoração e Arquitetura

## Objetivo
Usar Gemini CLI para melhorar legibilidade, performance e aderência arquitetural.

## 1) Refatoração de código legado
Cenário da aula:
- Função de listagem na API com loops aninhados e baixa legibilidade.

Meta:
- Reduzir complexidade
- Tornar regras de negócio explícitas
- Manter comportamento externo

## 2) Adequação de padrões de projeto
Aplicar padrões quando fizer sentido:
- Service + Repository no NestJS
- Camada de acesso a dados isolada em `packages/db`
- Mapeamento de DTO no boundary da API

## 3) Estratégia prática no terminal
- Pedir refatoração incremental
- Exigir explicação das decisões
- Validar diffs pequenos por vez

## Critérios de aceite
- Menor complexidade ciclomática percebida
- Sem regressão funcional
- Responsabilidades melhor separadas
