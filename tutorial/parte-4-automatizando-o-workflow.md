# Parte 4 — Automatizando o Workflow (30 min)

## Objetivo
Escalar o uso do Gemini CLI com automações e pré-code-review local.

## 1) Scripts customizados (Bash/Python)
Casos práticos:
- Revisar arquivos modificados em lote
- Gerar sugestões de melhoria por módulo
- Criar resumo de mudanças para PR

Fluxo sugerido:
1. Capturar arquivos alterados via Git
2. Enviar contexto para Gemini CLI
3. Salvar saída em relatório local

## 2) Introdução ao code review via CLI
Antes do push:
- Rodar revisão automática local
- Identificar riscos de segurança
- Checar quebra de padrão arquitetural
- Priorizar pontos críticos para revisão humana

## Critérios de aceite
- Menos retrabalho no PR
- Feedback mais cedo
- Melhor qualidade média das mudanças
