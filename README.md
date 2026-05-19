# Mapeamento de contatos institucionais de cursos de História

Mapeamento auditável de universidades públicas brasileiras com cursos de História e de seus contatos institucionais relacionados a secretaria acadêmica, seção de alunos, coordenação, departamento, instituto, centro ou chefia.

O projeto combina base oficial do Inep com apuração documental em fontes institucionais. A proposta não é apenas reunir e-mails: é produzir um mapa verificável, com critério de seleção, fonte, data de verificação, ressalvas e tratamento explícito dos casos em que a evidência pública não foi suficiente.

Neste recorte, "completo" significa cobrir todo o universo de universidades públicas definido pelos critérios do Inep usados no projeto e classificar todos os registros com curso de História, inclusive quando a conclusão é a ausência de contato oficial permanente publicado.

## Entregáveis principais

- `mapeamento_contatos_institucionais_historia_universidades_publicas.xlsx`: planilha final consolidada.
- `base_auditavel_universidades_publicas_cursos_historia.xlsx`: base auditável anterior à consolidação final.
- `archive/sprints/`: versões intermediárias por etapa de apuração.
- `scripts/build_historia_universidades.py`: script que reconstrói a base inicial a partir dos microdados oficiais do Inep.

## Resultado consolidado

- 116 universidades públicas brasileiras identificadas na base oficial.
- 94 universidades públicas com ao menos um curso de História.
- 254 cursos de História identificados no Censo da Educação Superior 2024.
- 94 registros finais de universidades com História.
- 0 registros pendentes na planilha final.
- 68 registros `Apurado`.
- 24 registros `Apurado com ressalva`.
- 2 registros `Não encontrado`, quando não foi localizado e-mail oficial permanente em fonte institucional.
- 173 e-mails únicos com sintaxe básica validada.

## Documentação

- [Metodologia](docs/metodologia.md)
- [Dados e reprodutibilidade](docs/dados-e-reprodutibilidade.md)
- [Estrutura das planilhas](docs/estrutura-das-planilhas.md)
- [Dicionário de dados](docs/dicionario-de-dados.md)
- [Diário técnico](AGENT.md)

## Padrão de rigor

Este repositório segue quatro regras de qualidade:

- **Fonte oficial primeiro**: a identificação das instituições e cursos parte do Censo da Educação Superior 2024.
- **Crítica de fonte**: páginas, documentos e contatos são tratados conforme origem, atualidade, vínculo institucional e adequação ao uso.
- **Rastreabilidade**: contatos preenchidos devem manter URL, data de verificação e observação quando houver limitação.
- **Não inferência**: e-mails não são criados por padrão de domínio nem completados por suposição.
- **Ressalva explícita**: contatos indiretos, pessoais institucionais, multicampi, protegidos por anti-spam ou de pós-graduação são marcados como `Apurado com ressalva`.

## Estrutura do repositório

```text
.
|-- AGENT.md
|-- README.md
|-- archive/
|   `-- sprints/
|-- docs/
|-- scripts/
|   `-- build_historia_universidades.py
|-- base_auditavel_universidades_publicas_cursos_historia.xlsx
`-- mapeamento_contatos_institucionais_historia_universidades_publicas.xlsx
```

Os microdados brutos do Inep ficam fora do Git por tamanho e por serem uma fonte pública externa. As instruções para recompor esses arquivos estão em [Dados e reprodutibilidade](docs/dados-e-reprodutibilidade.md).

## Como preparar o ambiente

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Como reconstruir a base oficial

Baixe e extraia os Microdados do Censo da Educação Superior 2024 do Inep em:

```text
data/raw/microdados_censo_da_educacao_superior_2024/dados/
```

Com os arquivos:

- `MICRODADOS_ED_SUP_IES_2024.CSV`
- `MICRODADOS_CADASTRO_CURSOS_2024.CSV`

Depois rode:

```bash
python3 scripts/build_historia_universidades.py --output base_universidades_publicas_cursos_historia.xlsx
```

Esse comando reconstrói a base oficial inicial. A planilha final inclui uma etapa posterior de apuração documental de contatos institucionais.
