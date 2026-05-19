# Metodologia

## Pergunta de trabalho

Quais universidades públicas brasileiras possuem cursos de História e quais contatos institucionais publicamente verificáveis podem ser usados para comunicação com as estruturas acadêmicas ligadas a esses cursos?

## Escopo

Inclui:

- universidades públicas brasileiras registradas no Censo da Educação Superior 2024;
- cursos de História identificados na base oficial do Inep;
- contatos institucionais vinculados a secretaria, seção de alunos, coordenação, departamento, centro, instituto, faculdade ou chefia;
- fontes oficiais ou institucionais com URL e data de verificação.

Não inclui:

- instituições privadas;
- centros universitários, faculdades isoladas, IFs ou Cefets quando não classificados como universidade pela variável usada;
- cursos de História da Arte;
- e-mails inferidos por padrão de domínio;
- contatos sem lastro documental público.

## Fonte-base

A fonte estruturante é o Censo da Educação Superior 2024, publicado pelo Inep.

Arquivos usados:

- `MICRODADOS_ED_SUP_IES_2024.CSV`
- `MICRODADOS_CADASTRO_CURSOS_2024.CSV`

## Critérios de seleção

Universidade pública:

- `TP_ORGANIZACAO_ACADEMICA=1`
- `TP_REDE=1`

Curso de História:

- `NO_CURSO` contém `História`;
- `TP_DIMENSAO=1`, para considerar linhas locais;
- exclusão de cursos classificados como `História da Arte`.

Esses critérios produzem um universo fechado de 116 universidades públicas, das quais 94 têm ao menos um curso de História.

## Apuração documental dos contatos

A etapa de contatos foi tratada como apuração documental, não como preenchimento automático.

Fontes aceitas:

- páginas oficiais da universidade;
- páginas de curso, departamento, coordenação, centro, instituto ou faculdade;
- páginas de pró-reitoria, registro acadêmico, seção de alunos ou secretaria;
- documentos oficiais publicados em domínio institucional;
- páginas de programas institucionais quando o contato direto do curso não estava publicamente disponível, sempre com ressalva.

Fontes não aceitas como evidência suficiente:

- agregadores comerciais;
- páginas sem vínculo institucional claro;
- e-mails deduzidos por padrão;
- contatos pessoais sem publicação institucional;
- conteúdo sem URL rastreável.

## Crítica de fonte

Cada contato foi interpretado conforme quatro dimensões:

- origem: se a página ou documento pertence à universidade ou a estrutura institucional vinculada;
- proximidade: se o contato é diretamente do curso/departamento ou se é um canal acadêmico indireto;
- atualidade: se a fonte parece ativa e compatível com o uso pretendido;
- suficiência: se a evidência permite usar o e-mail sem extrapolação.

Quando uma dessas dimensões era fraca, o registro foi mantido com ressalva em vez de ser apresentado como contato plenamente apurado.

## Classificação dos resultados

- `Apurado`: contato localizado em fonte oficial ou institucional e adequado ao uso.
- `Apurado com ressalva`: contato localizado, mas com limitação relevante, como multicampi, contato indireto, e-mail pessoal institucional, proteção anti-spam, página antiga, fonte de pós-graduação ou ausência de e-mail genérico do curso.
- `Não encontrado`: não foi localizado e-mail oficial permanente de secretaria, coordenação, departamento ou estrutura equivalente.

## Tratamento da incerteza

A ausência de evidência foi preservada como dado. Quando a fonte pública não permitiu confirmar um e-mail direto, o registro foi marcado com ressalva ou como `Não encontrado`; não houve preenchimento por adivinhação.

Esse procedimento é importante para manter o valor histórico e documental do levantamento: a planilha registra tanto o contato encontrado quanto os limites de visibilidade pública das instituições.

## Completude do mapeamento

O mapeamento é completo dentro do recorte definido: todas as universidades públicas identificadas pelos critérios do projeto foram classificadas, e todas as universidades com curso de História receberam um status final de apuração.

Completude, aqui, não significa que toda instituição publique um e-mail direto e permanente. Significa que cada caso foi examinado, classificado e documentado conforme a evidência disponível.

## Validações finais

- Conferência da cobertura: 94 universidades públicas com História na planilha final.
- Checagem de ausência de registros pendentes.
- Deduplicação de e-mails consolidados.
- Validação básica de sintaxe dos e-mails.
- Preservação de fontes, datas de verificação e observações de ressalva.
