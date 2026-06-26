# Parte 5 — Encerramento, Limitações e Próximos Passos (10 min)

## Objetivo
Consolidar visão crítica sobre uso de IA na engenharia de software.

## 1) O “Alucinômetro”
Como detectar alucinação:
- API/função que não existe na versão usada
- Dependência sugerida sem necessidade
- Resultado incompatível com arquitetura do projeto

Como reagir:
- Validar com documentação oficial
- Executar testes/lint/build
- Revisar diff com foco em lógica e segurança

## 2) Papel do engenheiro
A IA acelera, mas não substitui:
- Julgamento arquitetural
- Decisão de trade-offs
- Validação de regras de negócio
- Responsabilidade por qualidade e segurança

## 3) Q&A e discussão
Perguntas orientadoras:
- Onde IA mais reduziu tempo no seu fluxo?
- Quais tipos de tarefa ainda exigem revisão pesada?
- Que guardrails vamos adotar em equipe?

## Próximos passos sugeridos
- Padronizar prompts por tipo de tarefa
- Integrar revisão por IA ao pipeline de PR
- Definir checklist oficial de validação humana
