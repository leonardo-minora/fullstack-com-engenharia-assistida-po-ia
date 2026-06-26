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

## Passo a passo do checklist (com comandos)

### 1) CLI instalado
1. Verifique se o `node` e o `npm` estão instalados:
   ```bash
   node -v
   npm -v
   ```
2. Instale o Gemini CLI (ajuste conforme a documentação da versão adotada):
   ```bash
   npm install -g @google/gemini-cli
   ```
3. Valide a instalação:
   ```bash
   gemini --help
   ```

### 2) `GEMINI_API_KEY` carregada
1. Defina a variável no shell atual:
   ```bash
   export GEMINI_API_KEY="SUA_CHAVE_AQUI"
   ```
2. Confirme se a variável foi carregada:
   ```bash
   printenv GEMINI_API_KEY
   ```
3. (Opcional) Para uso local, salve em `.env` (não versionado) com permissão restrita:
   ```bash
   touch .env
   grep -q '^GEMINI_API_KEY=' .env || echo 'GEMINI_API_KEY="SUA_CHAVE_AQUI"' >> .env
   chmod 600 .env
   ```
4. Carregue a variável a partir do `.env` no shell atual:
   ```bash
   set -a
   source .env
   set +a
   ```

### 3) Hello World executado
1. Consulte a sintaxe de envio de prompt da versão instalada (os comandos podem variar entre versões):
   ```bash
   gemini --help
   ```
2. Execute um prompt simples no terminal (exemplo para versões que aceitam prompt direto):
   ```bash
   gemini "responda apenas: Hello World"
   ```
3. Confirme que a resposta ocorreu sem erro de autenticação.

### 4) Regras de segurança aplicadas
1. Verifique se `.env` está ignorado:
   ```bash
   grep '^\.env$' .gitignore
   ```
2. Garanta que `.env.example` não contém segredo real:
   ```bash
   cat .env.example
   ```
3. Antes de commitar, confira se não há segredos rastreados:
   ```bash
   git status
   git diff
   ```
