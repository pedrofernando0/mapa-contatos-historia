# Dicionário de dados

Este dicionário descreve os principais campos usados nas planilhas. Os nomes das colunas foram preservados próximos aos microdados oficiais quando ajudam na rastreabilidade.

## Identificação institucional

- `CO IES`: código da instituição no Inep.
- `SG IES`: sigla da instituição.
- `NO IES`: nome oficial da instituição.
- `NO REGIAO IES`: região da instituição.
- `SG UF IES`: unidade federativa.
- `NO MUNICIPIO IES`: município da instituição.
- `Categoria Administrativa`: categoria administrativa registrada na base oficial.

## Curso de História

- `Tem Curso Historia`: indica se a universidade tem ao menos um curso de História segundo os critérios do projeto.
- `Qtd Cursos Historia`: quantidade de cursos de História identificados.
- `Modalidades Historia`: modalidades encontradas, como presencial ou EaD.
- `Graus Historia`: graus acadêmicos encontrados.
- `Matriculas Historia 2024`: matrículas em cursos de História no ano-base.
- `Vagas Historia 2024`: vagas em cursos de História no ano-base.
- `CO CURSO`: código do curso no Inep.
- `NO CURSO`: nome do curso na base oficial.
- `NO CINE ROTULO`: classificação Cine Brasil usada no Censo.

## Contatos institucionais

- `Email Secao Alunos`: contato de seção de alunos, registro acadêmico ou estrutura equivalente.
- `Email Secretaria Curso Historia`: contato de secretaria ou coordenação do curso de História.
- `Email Departamento Historia`: contato de departamento, área, centro, instituto ou estrutura acadêmica relacionada à História.
- `Email Chefe Departamento`: contato de chefia, coordenação ou responsável acadêmico quando publicado oficialmente.
- `Emails Consolidados`: conjunto de e-mails úteis reunidos para a instituição.
- `Qtd Emails Unicos`: quantidade de e-mails únicos associados ao registro.

## Fonte e auditoria

- `Fonte Email`: descrição sintética da fonte usada.
- `Url Fonte Email`: URL da página ou documento institucional consultado.
- `Data Verificacao Email`: data em que a fonte foi verificada.
- `Status Apuracao Email`: classificação final da apuração.
- `Observacoes`: justificativas, limitações, contexto multicampi ou ressalvas.
- `Pendencia Final`: ação recomendada ou limitação que permanece após a revisão.

## Status de apuração

- `Apurado`: contato institucional adequado localizado.
- `Apurado com ressalva`: contato localizado com limitação relevante.
- `Não encontrado`: e-mail oficial permanente não localizado em fonte institucional.

## Leitura recomendada

Para uso operacional, comece pela aba `Contatos_Historia` da planilha final.

Para auditoria metodológica, compare:

- `Resumo`;
- `Pendencias_Finais`;
- `Fontes_Revisao_Final`;
- `Fontes_Sprint3`;
- versões em `archive/sprints/`.
