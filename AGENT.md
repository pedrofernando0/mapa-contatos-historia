# Diário técnico do projeto

## 2026-05-11

Contexto: início do projeto para listar todas as universidades públicas do Brasil, verificar presença de curso de História e organizar a apuração de e-mails institucionais em planilha.

Decisões:

- Fonte-base oficial: Microdados do Censo da Educação Superior 2024, Inep.
- Critério de universidade pública: `TP_ORGANIZACAO_ACADEMICA=1` e `TP_REDE=1`.
- Critério de curso de História: `NO_CURSO` contém `História`, em linhas locais `TP_DIMENSAO=1`.
- Cursos classificados como `História da arte` foram excluídos da marcação de curso de História.
- E-mails não foram inventados nem inferidos por domínio; a planilha deixa esses campos como pendentes para apuração por fonte oficial.

Arquivos criados:

- `scripts/build_historia_universidades.py`
- `lista_universidades_publicas_historia.xlsx`
- `README.md`

Resultado da Sprint 0:

- 116 universidades públicas listadas.
- 94 universidades públicas com curso de História.
- 254 cursos de História identificados.
- Planilha com sprints, fontes, pendências e campos de contato.

Próximos passos:

- Executar Sprint 1: apurar e-mails oficiais das universidades com História nas regiões Norte e Centro-Oeste.
- Preencher sempre `url_fonte_email` e `data_verificacao_email`.
- Marcar como `Não encontrado` apenas após busca em páginas oficiais da universidade, departamento, curso e pró-reitoria/registro acadêmico.

Resultado da Sprint 1:

- Arquivo gerado: `lista_universidades_publicas_historia_sprint1.xlsx`.
- A planilha principal estava aberta no LibreOffice (`.~lock.lista_universidades_publicas_historia.xlsx#`), então a Sprint 1 foi salva em uma cópia para evitar conflito de gravação.
- 24 universidades com curso de História nas regiões Norte e Centro-Oeste foram revisadas.
- 20 registros ficaram como `Apurado`.
- 2 registros ficaram como `Apurado com ressalva`: UFR, por bloqueio Cloudflare no acesso direto via terminal, e UEPA, por contato oficial publicado em notícia antiga de 2018.
- 2 registros ficaram como `Não encontrado`: UEA e UFAM, porque não foi localizado contato permanente oficial de secretaria/coordenação/departamento de História.
- As abas `Universidades`, `Pendencias_Email`, `Sprints` e `Fontes` foram atualizadas na cópia da Sprint 1 com e-mails, URLs, data de verificação e observações.

Próximos passos atualizados:

- Quando o arquivo principal for fechado no LibreOffice, substituir ou reconciliar com `lista_universidades_publicas_historia_sprint1.xlsx`.
- Executar Sprint 2: apurar e-mails oficiais das universidades com História na região Nordeste.

Resultado da Sprint 2:

- Arquivo gerado: `lista_universidades_publicas_historia_sprint2.xlsx`.
- A Sprint 2 partiu da cópia da Sprint 1, preservando a planilha principal e a cópia da Sprint 1 que estavam abertas no LibreOffice.
- 30 universidades com curso de História na região Nordeste foram revisadas.
- 22 registros ficaram como `Apurado`.
- 6 registros ficaram como `Apurado com ressalva`, principalmente por contatos pessoais institucionais, múltiplos campi/ofertas ou e-mails externos publicados em fonte oficial.
- 2 registros ficaram como `Não encontrado`: UNEAL e URCA, porque não foi localizado contato permanente oficial de secretaria/coordenação/departamento de História.
- As abas `Universidades`, `Pendencias_Email`, `Sprints` e `Fontes` foram atualizadas na cópia da Sprint 2 com e-mails, URLs, data de verificação e observações.

Próximos passos atualizados:

- Quando os arquivos abertos no LibreOffice forem fechados, reconciliar a versão mais recente a partir de `lista_universidades_publicas_historia_sprint2.xlsx`.
- Executar Sprint 3: apurar e-mails oficiais das universidades com História na região Sudeste.

## 2026-05-18

Sessão de fechamento: apuração de Sudeste (22) + Sul (18) + revisão de pendentes (11). Executado em 6 waves paralelas.

Waves planejadas:
- Wave 1: MG (11) — UEMG, UNIMONTES, UNIFAL-MG, UFJF, UFMG, UFOP, UFSJ, UFU, UFV, UFTM, UFVJM
- Wave 2: ES + RJ (6) — UFES, UERJ, UNIRIO, UFRJ, UFF, UFRRJ
- Wave 3: SP (5) — USP, UNICAMP, UNESP, UNIFESP, UNITAU
- Wave 4: PR (9) — UEL, UEM, UEPG, UNICENTRO, UNIOESTE, UFPR, UNILA, UENP, UNESPAR
- Wave 5: RS + SC (9) — UNIPAMPA, UFPEL, UFSM, FURG, UFRGS, UDESC, UFFS, UFSC, FURB
- Wave 6: Revisão (11) — UNEAL, UEA, UFAM, UNEB, URCA, UEMA, UFR, UEPA, UEPB, UNIVASF, UPE, UESPI

Resultado das waves 1–5 (executadas em paralelo):

- Arquivo gerado: `lista_universidades_publicas_historia_sprint3.xlsx`.
- 40 universidades do Sudeste e Sul apuradas.
- Resultado consolidado: 68 Apurado | 20 Apurado com ressalva | 6 Não encontrado (de 94 totais).

Casos hand-picked — requerem ação manual (não recuperáveis automaticamente):

| Sigla | Motivo | Como resolver |
|---|---|---|
| UNESP (Assis) | Emails protegidos por JS no site da FCL | Ligar (18) 3302-5800, pedir email da STG de História |
| UNESP (Franca) | Emails protegidos por JS no site da FCHS | Ligar (16) 3706-8700, pedir email da STG de História |
| UENP | Site retorna HTTP 403 para acesso automatizado | Ligar (43) 3511-4300 (CCHE-CJ Campus Jacarezinho) |
| UNIOESTE (Marechal Rondon) | Email protegido por anti-spambot no site | Ligar (45) 3284-7863, ou acessar com navegador JS |
| UNIFESP | Email do departamento protegido por anti-spam | Acessar https://unifesp.br/campus/gua/... com navegador |
| UNEAL | Sem email permanente publicado em fonte oficial | Acessar Moodle oficial ou ligar para seção acadêmica |
| UEA | Apenas email temporário de PS encontrado | Ligar para secretaria do curso de História |
| UFAM | Só telefone listado no site oficial | Tentar via formulário web ou portal do departamento |
| URCA | ch@urca.br genérico, sem contato direto do curso | Ligar para Centro de Humanidades; confirmar endereço específico |

Próximos passos:
- Wave 6 (revisão): tratar casos com ressalva e não encontrados acima.
- Casos hand-picked: resolver via ligação ou acesso manual com navegador.
- Quando concluído, consolidar planilha final e atualizar aba Fontes.

Resultado da revisão final e consolidação:

- Arquivo final gerado: `lista_emails_departamentos_historia_final.xlsx`.
- Base usada: `lista_universidades_publicas_historia_sprint3.xlsx`.
- Estrutura do arquivo final: `Contatos_Historia`, `Resumo`, `Pendencias_Finais`, `Emails_Unicos`, `Fontes_Revisao_Final` e `Fontes_Sprint3`.
- Validação final: 94 universidades públicas com História, 0 registros `Pendente`, 68 `Apurado`, 24 `Apurado com ressalva`, 2 `Não encontrado`.
- E-mails consolidados: 173 e-mails únicos, todos com sintaxe básica válida.
- Casos recuperados da lista de `Não encontrado`:
  - `UFAM`: localizado `chefia_historia@ufam.edu.br` em PDF oficial UFAM/ICHL; mantido como `Apurado com ressalva`.
  - `URCA`: localizados `profhistoria@urca.br` e `profhistoriaurca.secretaria@urca.br` na página oficial do ProfHistória/URCA; mantido como `Apurado com ressalva`, por ser contato de pós-graduação.
  - `UENP`: localizado `luis.ernesto@uenp.edu.br` em material oficial UENP e página de contato do Campus Jacarezinho; mantido como `Apurado com ressalva`, por ser contato pessoal institucional e não e-mail genérico de colegiado.
  - `UNESP`: localizados `graduacao@assis.unesp.br`, `grad@franca.unesp.br`, `graduacao.fclar@unesp.br` e `dephist@franca.unesp.br` em fontes oficiais dos campi; mantido como `Apurado com ressalva`, por multicampi e proteção anti-spam/JS em parte dos contatos.
- Casos que permaneceram `Não encontrado`: `UNEAL` e `UEA`, porque não foi localizado e-mail oficial permanente de secretaria/coordenação/departamento de História.
- Casos ainda com ressalva operacional explícita: `UNIFESP`, `UNIOESTE`, `UEMG` e os multicampi/pessoais/institucionais listados na aba `Pendencias_Finais`.
- Organização da pasta: versões intermediárias movidas para `archive/sprints/`; `docs/` vazio movido para `archive/docs/`; `sprint3` mantida na raiz como base auditável.

Sessão de publicação no GitHub:

- Documentação reorganizada em `README.md` e `docs/`.
- Criados documentos de metodologia, dados/reprodutibilidade e estrutura das planilhas.
- Criado `requirements.txt` com dependências mínimas (`pandas` e `openpyxl`).
- Criado `.gitignore` para excluir cache Python, arquivos temporários/lock e microdados brutos em `data/raw/`.
- Decisão de versionamento: incluir script, documentação, planilha final, planilha Sprint 3 e arquivos pequenos de auditoria em `archive/sprints/`; não versionar CSV/ZIP brutos do Inep por tamanho e por serem fonte pública externa.
- Repositório remoto: `pedrofernando0/lista-emails-historia`, privado.
