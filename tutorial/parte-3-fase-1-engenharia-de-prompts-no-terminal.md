# Parte 3 — Fase 1: Engenharia de Prompts no Terminal

## Objetivo
Montar prompts claros no terminal para gerar alterações úteis e consistentes no monorepo.

## Cenário da fase
Aplicativo: rede social para compartilhamento de prompts.

Regras funcionais desta fase:
- CRUD básico de prompts
- Etiquetas (tags) por prompt
- Reações de gostar e não gostar
- Pesquisa de prompts por texto e etiqueta

## Contexto do projeto
- API NestJS em `apps/api`
- Web Next.js em `apps/web`
- Persistência PostgreSQL em `packages/db`

## Checklist rápido
- [ ] Levantar arquivos de contexto antes de pedir alterações
- [ ] Escrever prompt com objetivo, escopo e critérios de aceite
- [ ] Executar geração incremental (API primeiro, depois Web)
- [ ] Revisar o resultado e pedir ajustes objetivos

## Passo a passo no terminal (com comandos)
> Substitua `<comando-cli>` pelo comando da IA no seu ambiente (ex.: `gemini`, se esse for o binário instalado).

### 1) Levantar contexto do monorepo
1. Entre na raiz do projeto:
   ```bash
   cd /caminho/para/seu/projeto
   ```
2. Liste arquivos principais da API, Web e DB:
   ```bash
   ls
   find apps -maxdepth 3 -type f | head -n 40   # aumente 40 se o projeto for maior
   find packages -maxdepth 3 -type f | head -n 40   # aumente 40 se necessário
   ```
3. Localize arquivos relacionados ao domínio de prompts:
   ```bash
   grep -RInE --exclude-dir=node_modules --exclude-dir=.next --include="*.ts" --include="*.tsx" "prompt|tag|search|like|dislike" apps packages
   ```

### 2) Separar os arquivos que irão para o contexto
Selecione somente arquivos necessários:
- Schema/model do banco
- DTOs/entidades/contratos da API
- Arquivos-alvo da feature no frontend

Comandos úteis para confirmar:
```bash
find apps/api -type f | grep -E "dto|entity|controller|service|module"
find apps/web -type f | grep -E "page|component|api|hook"
find packages/db -type f
```

### 3) Construir um prompt eficiente
Monte o prompt com a estrutura abaixo:
1. Papel da IA
2. Objetivo exato
3. Restrições técnicas
4. Escopo de arquivos
5. Critérios de aceite

Exemplo (copie e ajuste):
```bash
<comando-cli> "
Atue como engenheiro fullstack sênior em monorepo com NestJS + Next.js + PostgreSQL.
Objetivo: implementar a fase inicial de uma rede social de prompts.
Escopo:
- Prompt possui: id, título, conteúdo, etiquetas[]
- Permitir gostar e não gostar por prompt
- Permitir pesquisa por texto e etiqueta
Restrições:
- Manter padrões já existentes do repositório
- Não criar dependências novas sem necessidade
- Não expor dados sensíveis
Critérios de aceite:
- Endpoints da API para criar/listar prompts e reagir com like/dislike
- Pesquisa por texto e etiqueta funcionando
- Tela web com listagem e campo de pesquisa
- Código organizado e coerente com a base atual
"
```

### 4) Pedir implementação incremental
1. Primeiro, solicite só API:
   ```bash
   <comando-cli> "Com base nos arquivos de contexto, implemente somente API (NestJS) para prompts, etiquetas, like/dislike e pesquisa."
   ```
2. Depois, solicite só Web:
   ```bash
   <comando-cli> "Agora implemente somente a interface web (Next.js) para listar prompts, pesquisar por texto/etiqueta e reagir com like/dislike."
   ```
3. Se necessário, peça ajustes cirúrgicos:
   ```bash
   <comando-cli> "Ajuste apenas os arquivos de pesquisa para suportar filtro combinado de texto + etiqueta, sem alterar o restante."
   ```

### 5) Revisar resposta e refinar prompt
Após cada execução:
1. Verifique se a IA respeitou o escopo.
2. Se faltou algo, peça correção objetiva.
3. Evite prompts vagos como “melhore tudo”.

Exemplo de refinamento:
```bash
<comando-cli> "Refaça apenas o endpoint de pesquisa para retornar paginação e ordenar por número de likes, mantendo os mesmos DTOs."
```

## Critérios de qualidade da fase
- Código claro e legível
- Sem quebra de padrão do monorepo
- Mudanças incrementais e fáceis de revisar
- Sem exposição de dados sensíveis
