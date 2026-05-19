# Lista de e-mails - cursos de Historia em universidades publicas

Projeto para consolidar uma lista auditavel de universidades publicas brasileiras com curso de Historia e seus contatos institucionais de secretaria, secao de alunos, departamento ou chefia.

## Entregaveis principais

- `lista_emails_departamentos_historia_final.xlsx`: planilha final consolidada, pronta para uso.
- `lista_universidades_publicas_historia_sprint3.xlsx`: base auditavel usada antes da consolidacao final.
- `archive/sprints/`: versoes intermediarias das sprints de apuracao.
- `scripts/build_historia_universidades.py`: script que regenera a base inicial a partir dos microdados oficiais do Inep.

## Resultado consolidado

- 94 universidades publicas com curso de Historia.
- 0 registros pendentes.
- 68 registros `Apurado`.
- 24 registros `Apurado com ressalva`.
- 2 registros `Nao encontrado`, quando nao foi localizado e-mail oficial permanente apos busca em fontes institucionais.
- 173 e-mails unicos com sintaxe basica validada.

## Documentacao

- [Metodologia](docs/metodologia.md)
- [Dados e reprodutibilidade](docs/dados-e-reprodutibilidade.md)
- [Estrutura das planilhas](docs/estrutura-das-planilhas.md)
- [Diario tecnico](AGENT.md)

## Estrutura do repositorio

```text
.
|-- AGENT.md
|-- README.md
|-- archive/
|   `-- sprints/
|-- docs/
|-- scripts/
|   `-- build_historia_universidades.py
|-- lista_emails_departamentos_historia_final.xlsx
`-- lista_universidades_publicas_historia_sprint3.xlsx
```

Os microdados brutos do Inep ficam fora do Git por tamanho e por serem uma fonte publica externa. As instrucoes para recompor esses arquivos estao em [Dados e reprodutibilidade](docs/dados-e-reprodutibilidade.md).

## Como preparar o ambiente

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Como regenerar a base inicial

Baixe e extraia os Microdados do Censo da Educacao Superior 2024 do Inep em:

```text
data/raw/microdados_censo_da_educacao_superior_2024/dados/
```

Com os arquivos:

- `MICRODADOS_ED_SUP_IES_2024.CSV`
- `MICRODADOS_CADASTRO_CURSOS_2024.CSV`

Depois rode:

```bash
python3 scripts/build_historia_universidades.py --output lista_universidades_publicas_historia.xlsx
```

## Regra de preenchimento de e-mails

Usar apenas paginas oficiais ou institucionais. Para cada e-mail preenchido, registrar:

- e-mail encontrado;
- tipo de contato;
- URL da fonte;
- data de verificacao;
- observacao quando o contato for indireto, pessoal institucional, multicampi ou precisar de confirmacao.
