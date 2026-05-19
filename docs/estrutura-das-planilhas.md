# Estrutura das planilhas

## Planilha final

Arquivo:

- `mapeamento_contatos_institucionais_historia_universidades_publicas.xlsx`

Uso:

- consultar os contatos consolidados;
- verificar status de apuração;
- examinar ressalvas e pendências finais;
- recuperar fontes usadas na etapa final.

Abas:

- `Contatos_Historia`: tabela principal com universidades, contatos, fontes, status e observações.
- `Resumo`: métricas finais da consolidação.
- `Pendencias_Finais`: casos com ressalva operacional ou sem contato oficial permanente localizado.
- `Emails_Unicos`: relação deduplicada de e-mails consolidados.
- `Fontes_Revisao_Final`: fontes usadas na revisão final.
- `Fontes_Sprint3`: fontes acumuladas na etapa anterior.

## Base auditável

Arquivo:

- `base_auditavel_universidades_publicas_cursos_historia.xlsx`

Uso:

- auditar o universo de universidades públicas;
- conferir cursos de História identificados no Censo/Inep;
- rastrear a evolução antes da consolidação final.

Abas:

- `Resumo`: critérios e contagens da base.
- `Universidades`: todas as universidades públicas identificadas pelos critérios do projeto.
- `Cursos_Historia`: cursos de História encontrados na base oficial.
- `Pendencias_Email`: fila de universidades com História e status de apuração na etapa anterior.
- `Sprints`: plano de execução por etapas.
- `Fontes`: fontes consultadas durante a apuração.

## Arquivos históricos

Pasta:

- `archive/sprints/`

Arquivos:

- `00_base_inicial_universidades_publicas_historia.xlsx`
- `01_apuracao_norte_centro_oeste.xlsx`
- `02_apuracao_nordeste.xlsx`

Uso:

- preservar versões intermediárias;
- permitir comparação entre etapas;
- manter rastreabilidade do processo de apuração.

## Convenção de nomes

Os nomes foram padronizados para diferenciar três camadas:

- `mapeamento_...`: produto final de contatos institucionais.
- `base_auditavel_...`: base de verificação e rastreabilidade.
- `archive/sprints/NN_...`: etapas históricas do trabalho.
