# Dados e reprodutibilidade

## Dados brutos

Os microdados brutos do Inep nao sao versionados neste repositorio porque somam centenas de MB e podem ser obtidos diretamente da fonte oficial.

Fonte:

- Inep - Microdados do Censo da Educacao Superior
- https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/censo-da-educacao-superior

Arquivo usado:

- `microdados_censo_da_educacao_superior_2024.zip`

## Estrutura esperada localmente

Para regenerar a base inicial, extraia os arquivos CSV para:

```text
data/raw/microdados_censo_da_educacao_superior_2024/dados/
```

Arquivos obrigatorios:

- `MICRODADOS_ED_SUP_IES_2024.CSV`
- `MICRODADOS_CADASTRO_CURSOS_2024.CSV`

## Regeneracao da base inicial

Com as dependencias instaladas:

```bash
python3 scripts/build_historia_universidades.py --output lista_universidades_publicas_historia.xlsx
```

Esse comando recria a planilha-base com universidades publicas, cursos de Historia, pendencias de contato, sprints e fontes iniciais.

## O que nao e reproduzido automaticamente

A planilha final inclui apuracao manual/assistida de e-mails em sites oficiais das universidades. Essa etapa depende de navegacao, paginas institucionais e revisao de fontes, por isso nao e totalmente reproduzida pelo script.

As evidencias e decisoes dessa apuracao estao preservadas em:

- `lista_emails_departamentos_historia_final.xlsx`
- `lista_universidades_publicas_historia_sprint3.xlsx`
- `archive/sprints/`
- `AGENT.md`
