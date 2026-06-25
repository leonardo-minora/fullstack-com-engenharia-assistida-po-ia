# Parte 3 — Fase 3: Criação de Testes Automatizados

## Objetivo
Gerar rapidamente testes úteis para API, frontend e integração com banco.

## 1) Testes unitários e de integração
Foco da fase:
- Unitários para services da API NestJS
- Integração para rotas críticas
- Testes de componentes/páginas no Next.js

## 2) Estratégias de mocking com IA
Boas práticas:
- Mockar dependências externas (HTTP, fila, serviços terceiros)
- Isolar banco em teste (mock ou ambiente dedicado)
- Evitar testes acoplados à implementação interna

## 3) Prompt de geração de testes
Peça sempre:
- Cenários felizes e de erro
- Casos de borda
- Nomes de teste descritivos
- Cobertura mínima de regras críticas

## Critérios de aceite
- Testes reproduzíveis
- Falham quando regra quebra
- Documentam comportamento esperado
