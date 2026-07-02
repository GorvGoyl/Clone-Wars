---
description: Adiciona um novo clone/alternativa ao README.md do Clone Wars, na tabela e posição corretas, seguindo o guia de contribuição do projeto.
argument-hint: <descrição do clone: nome do site/app original, link do demo, link do repositório, link de tutorial (se houver), stack tecnológica>
---

Você vai adicionar uma nova entrada ao `README.md` deste projeto (Clone Wars), com base na descrição fornecida em: $ARGUMENTS

Este README contém duas tabelas markdown mantidas manualmente. Siga o processo abaixo **exatamente**, sem pular etapas.

## 1. Verificar estado do repositório antes de tocar em qualquer arquivo

Rode `git status --short`.

- Se não houver nenhuma alteração pendente, prossiga normalmente.
- Se houver alterações pendentes, avise o usuário quais arquivos estão afetados. Se essas alterações não forem claramente parte do trabalho atual (ex.: arquivos não relacionados a este comando, mudanças que você não fez agora), **pare e peça confirmação explícita** antes de continuar — não edite `README.md` por cima de um estado sujo sem o usuário saber.

## 2. Extrair as informações

A partir de $ARGUMENTS, identifique:
- Nome do site/app original que está sendo clonado (obrigatório)
- Link de demo (opcional)
- Link do repositório do clone (obrigatório ter pelo menos demo OU repo — não adicione uma linha sem nenhum link)
- Link de tutorial/curso (opcional — define em qual tabela a entrada vai)
- Stack tecnológica (obrigatório)

Se faltar o nome do clone, ou faltarem tanto demo quanto repo, **pare e pergunte ao usuário** antes de continuar. Não invente ou assuma valores.

## 3. Escolher a tabela correta

Leia `README.md` e localize as duas seções:
- **"Clones with Tutorials"** (por volta da linha 33) — usar quando houver link de tutorial/curso.
- **"Clones and Alternatives"** (por volta da linha 50) — usar quando NÃO houver link de tutorial.

## 4. Verificar duplicidade

Procure nas DUAS tabelas se já existe uma entrada para o mesmo site/app (mesmo nome, ou mesmo link de repo/demo).

- Se encontrar uma entrada idêntica ou muito parecida, **pare e avise o usuário** — não adicione duplicata.
- Exceção prevista no guia de contribuição: clones repetidos de apps triviais (ex.: Trello, 2048) só são aceitos se a stack tecnológica for claramente diferente da(s) já listada(s). Mesmo nesse caso, avise o usuário antes de inserir.

## 5. Verificar critério de funcionalidade mínima

O guia de contribuição do projeto proíbe clones "apenas de UI" (sem funcionalidade real). Avalie a descrição fornecida:
- Se não houver evidência de funcionalidade real (ex.: descrito explicitamente como "só front-end estático", "sem backend", "protótipo visual"), **pare e pergunte ao usuário** se ele confirma que o clone tem funcionalidade mínima antes de prosseguir.

## 6. Formatar a linha respeitando as colunas exatas da tabela escolhida

**Tabela "Clones with Tutorials"** (5 colunas):
`| Clone of | Demo | Tutorial / Course Site | Repo | Tech Stack |`

**Tabela "Clones and Alternatives"** (5 colunas):
`| Clone/Alt of | Demo | Repo | Tech stack | Repo Stars |`
- A coluna `Repo Stars` só existe nesta tabela. Preencha com o badge dinâmico, sem hardcodar número:
  `![GitHub Repo stars](https://img.shields.io/github/stars/<owner>/<repo>)`
- Antes de extrair `<owner>/<repo>` do link do repositório, **normalize a URL**: remova sufixo `.git`, barras finais (`/`), e quaisquer parâmetros de query ou fragmento (`?...`, `#...`). Só depois disso extraia owner/repo.
- Só inclua o badge se, após a normalização, o link for claramente do GitHub (`github.com/<owner>/<repo>`) e você conseguir extrair owner/repo com confiança. Caso contrário, deixe a célula vazia, seguindo o padrão já usado em linhas semelhantes na tabela.

Mantenha a mesma formatação de link markdown (`[texto](url)`) usada nas linhas vizinhas.

## 7. Inserir na posição alfabética correta

Compare o nome na primeira coluna (`Clone of` / `Clone/Alt of`) das linhas existentes, ignorando maiúsculas/minúsculas e acentuação, e insira a nova linha na posição alfabética correta dentro da tabela escolhida.

Use a ferramenta de edição para inserir apenas a linha nova entre as duas linhas vizinhas corretas — **não reescreva a tabela inteira** e não toque em nenhuma outra parte do README ou em qualquer outro arquivo do repositório.

## 8. Revisar antes de qualquer commit

Depois de editar:
1. Rode `git diff -- README.md` e mostre o resultado ao usuário.
2. Rode `git status --short` novamente e confirme que **somente `README.md`** aparece como alterado. Se qualquer outro arquivo aparecer modificado, avise o usuário imediatamente — isso não deveria acontecer.
3. **Não faça commit automaticamente.** Peça confirmação explícita do usuário antes de commitar, e só então use o fluxo normal de commit do projeto.

## Restrições

- Edite apenas `README.md`. Nunca modifique `LICENSE`, `.github/FUNDING.yml`, `_config.yml` ou qualquer outro arquivo.
- Se alguma informação necessária estiver ambígua ou faltando, pare e pergunte — não assuma.
