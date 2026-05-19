# Dados e reprodutibilidade

## Dados brutos

Os microdados brutos do Inep não são versionados neste repositório porque somam centenas de MB e podem ser obtidos diretamente da fonte pública oficial.

Fonte:

- Inep - Microdados do Censo da Educação Superior
- https://www.gov.br/inep/pt-br/acesso-a-informacao/dados-abertos/microdados/censo-da-educacao-superior

Arquivo usado:

- `microdados_censo_da_educacao_superior_2024.zip`

## Estrutura esperada localmente

Para reconstruir a base oficial inicial, extraia os CSVs para:

```text
data/raw/microdados_censo_da_educacao_superior_2024/dados/
```

Arquivos obrigatórios:

- `MICRODADOS_ED_SUP_IES_2024.CSV`
- `MICRODADOS_CADASTRO_CURSOS_2024.CSV`

## Dependências

```bash
python3 -m venv .venv
source .venv/bin/activate
pip install -r requirements.txt
```

## Reconstrução da base oficial

```bash
python3 scripts/build_historia_universidades.py --output base_universidades_publicas_cursos_historia.xlsx
```

O script gera uma planilha com:

- resumo dos critérios;
- universidades públicas;
- cursos de História;
- fila inicial de apuração de contatos;
- plano de sprints;
- fontes iniciais.

## O que é reproduzível por script

- identificação das universidades públicas;
- identificação dos cursos de História;
- contagens de cursos, vagas e matrículas;
- estrutura inicial da planilha de trabalho.

## O que depende de apuração documental

A planilha final inclui pesquisa manual/assistida em sites oficiais das universidades. Essa etapa não é totalmente reproduzida por script porque depende de páginas institucionais, documentos publicados, proteção anti-spam, páginas multicampi e julgamento documental.

As evidências e decisões dessa etapa estão preservadas em:

- `mapeamento_contatos_institucionais_historia_universidades_publicas.xlsx`
- `base_auditavel_universidades_publicas_cursos_historia.xlsx`
- `archive/sprints/`
- `AGENT.md`

## Política de versionamento dos dados

Versionado:

- scripts;
- documentação;
- planilhas finais e auditáveis de pequeno porte;
- versões intermediárias relevantes para rastreabilidade.

Não versionado:

- ZIP e CSVs brutos do Inep;
- caches locais;
- arquivos temporários ou locks de editor/planilha.
