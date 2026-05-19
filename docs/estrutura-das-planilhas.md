# Estrutura das planilhas

## `lista_emails_departamentos_historia_final.xlsx`

Planilha final consolidada.

Abas:

- `Contatos_Historia`: lista principal de universidades com curso de Historia, contatos encontrados, status e observacoes.
- `Resumo`: metricas finais da consolidacao.
- `Pendencias_Finais`: casos com ressalva operacional ou sem contato permanente localizado.
- `Emails_Unicos`: relacao deduplicada de e-mails e instituicoes associadas.
- `Fontes_Revisao_Final`: fontes usadas na etapa final de revisao.
- `Fontes_Sprint3`: fontes acumuladas na sprint anterior.

## `lista_universidades_publicas_historia_sprint3.xlsx`

Base auditavel anterior a consolidacao final.

Abas:

- `Resumo`: criterios e contagens da base.
- `Universidades`: todas as universidades publicas listadas.
- `Cursos_Historia`: cursos de Historia identificados no Censo/Inep.
- `Pendencias_Email`: fila de universidades com Historia e status de apuracao.
- `Sprints`: plano de execucao por etapas.
- `Fontes`: fontes consultadas durante a apuracao.

## `archive/sprints/`

Guarda versoes intermediarias das sprints para rastreabilidade:

- base inicial;
- Sprint 1;
- Sprint 2.

Esses arquivos permitem comparar a evolucao da apuracao antes da consolidacao final.
