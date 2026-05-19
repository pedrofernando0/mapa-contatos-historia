# Metodologia

## Objetivo

Identificar universidades publicas brasileiras com curso de Historia e consolidar contatos institucionais uteis para secretaria, secao de alunos, departamento, coordenacao ou chefia.

## Fonte-base

A base oficial usada para identificar universidades e cursos foi o Censo da Educacao Superior 2024, publicado pelo Inep.

## Criterios de selecao

Universidade publica:

- `TP_ORGANIZACAO_ACADEMICA=1`
- `TP_REDE=1`

Curso de Historia:

- `NO_CURSO` contem `Historia`
- linhas locais com `TP_DIMENSAO=1`
- cursos classificados como `Historia da Arte` foram excluidos

## Criterios de apuracao de e-mails

Foram aceitas apenas fontes oficiais ou institucionais, incluindo:

- paginas da universidade;
- paginas de curso, departamento, centro, instituto ou faculdade;
- paginas de pro-reitoria, registro academico ou secao de alunos;
- documentos oficiais publicados no dominio institucional.

E-mails nao foram inferidos por padrao de dominio. Quando nao havia fonte suficiente, o campo permaneceu sem e-mail direto e o status foi marcado como `Nao encontrado` ou `Apurado com ressalva`, conforme o caso.

## Status usados

- `Apurado`: contato localizado em fonte oficial/institucional e adequado ao uso.
- `Apurado com ressalva`: contato oficial localizado, mas com limitacao operacional, como contato pessoal institucional, multicampi, secretaria indireta, pos-graduacao ou protecao anti-spam.
- `Nao encontrado`: nao foi localizado e-mail oficial permanente de secretaria, coordenacao, departamento ou equivalente.

## Validacoes finais

- Consolidacao de 94 universidades publicas com Historia.
- Remocao de pendencias operacionais da fila principal.
- Validacao basica de sintaxe dos e-mails consolidados.
- Preservacao das fontes e observacoes de ressalva nas abas da planilha final.
