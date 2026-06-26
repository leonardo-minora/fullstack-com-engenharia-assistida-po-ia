# Parte 2 — Configuração do Ambiente Prático (15 min)

## Objetivo
Instalar, autenticar e validar o Gemini CLI com segurança no contexto do monorepo.

## 1) Instalação e autenticação
> Ajuste os comandos conforme a documentação da versão do Gemini CLI usada no seu ambiente.

Passos gerais:
1. Instalar o Gemini CLI
2. Exportar a variável de ambiente:
   - `GEMINI_API_KEY`
3. Validar se a variável está definida no shell atual

## 2) Primeiro teste (Hello World)
No terminal do monorepo, execute um prompt simples para validar:
- Perguntar algo curto (ex.: “responda apenas: Hello World”).

Critério de sucesso:
- O CLI responde sem erro de autenticação.

## 3) Boas práticas de segurança
- Nunca versionar `.env` com chave real
- Usar `.env.example` sem segredo
- Revisar `.gitignore` para arquivos sensíveis
- Em CI, armazenar chave em secret do provedor
- Nunca colar tokens em issue/PR pública

## Checklist rápido
- [ ] CLI instalado
- [ ] `GEMINI_API_KEY` carregada
- [ ] Hello World executado
- [ ] Regras de segurança aplicadas
