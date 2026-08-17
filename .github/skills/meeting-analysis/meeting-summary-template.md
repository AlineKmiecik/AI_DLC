---
artifact_type: meeting-analysis
schema_version: "1.0"
meeting_id: "<meeting-id>"
title: "<título da reunião>"
meeting_date: "<YYYY-MM-DD ou não informado>"
status: "draft"
revision: 1
handoff_ready: false
source_files: []
image_files: []
created_by: "Meeting Analyst"
created_at: "<data/hora ou não informado>"
updated_at: "<data/hora ou não informado>"
validated_by: null
validated_at: null
---

# Análise da reunião — <título>

## 1. Resumo executivo

- <Problema principal discutido>
- <Objetivo pretendido>
- <Decisão ou conclusão relevante>
- <Impacto relevante>
- <Principal dúvida ou bloqueio>

Máximo de oito itens.

## 2. Contexto e problema

### Contexto

<Descrição curta do cenário atual.>

### Problema

<Descrição objetiva do problema que motivou a reunião.>

### Resultado esperado mencionado

<Resultado esperado conforme discutido, sem transformá-lo em requisito formal.>

## 3. Decisões confirmadas

| ID | Decisão | Evidência | Confiança |
|---|---|---|---|
| DEC-01 | <decisão> | <timestamp, linha ou fonte> | Alta |

Use `Nenhum item identificado.` quando não houver decisões confirmadas.

## 4. Necessidades mencionadas

| ID | Necessidade | Origem | Situação |
|---|---|---|---|
| NEC-01 | <necessidade mencionada> | <fonte> | Mencionada / Confirmada pelo usuário |

Estas necessidades ainda não são histórias de usuário nem requisitos formais.

## 5. Regras e restrições citadas

| ID | Regra ou restrição | Evidência | Confiança |
|---|---|---|---|
| REG-01 | <regra ou restrição> | <fonte> | Alta / Média / Baixa |

## 6. Sistemas, áreas e pessoas envolvidas

### Sistemas

- <sistema>

### Áreas ou equipes

- <área ou equipe>

### Participantes relevantes para decisões ou ações

- <nome ou papel>

Não liste participantes que não sejam relevantes para o entendimento ou
para as ações.

## 7. Ações identificadas

| ID | Ação | Responsável | Prazo | Situação | Evidência |
|---|---|---|---|---|---|
| ACT-01 | <ação> | <pessoa ou equipe> | <prazo ou não informado> | Aberta | <fonte> |

## 8. Evidências visuais

| ID | Arquivo | Observação objetiva | Relação com a reunião | Hipótese ou dúvida |
|---|---|---|---|---|
| IMG-01 | <arquivo> | <o que é visível> | <relação confirmada> | <hipótese ou pergunta> |

Não trate hipóteses visuais como decisões confirmadas.

## 9. Dúvidas abertas

| ID | Dúvida | Quem pode responder | Impacto | Bloqueante | Origem |
|---|---|---|---|---|---|
| QST-01 | <pergunta> | <pessoa ou equipe> | <impacto> | Sim / Não | <fonte> |

## 10. Inconsistências e informações de baixa confiança

| ID | Informação | Motivo da incerteza | Possível interpretação | Ação necessária |
|---|---|---|---|---|
| UNC-01 | <informação> | <motivo> | <hipótese ou não informado> | <confirmação necessária> |

## 11. Itens explicitamente fora do escopo

- <item declarado fora do escopo>

Não inferir itens fora do escopo sem evidência.

## 12. Índice das fontes

| Fonte | Tipo | Identificação | Observação |
|---|---|---|---|
| SRC-01 | Transcrição | <caminho> | <informação relevante> |
| IMG-01 | Imagem | <arquivo> | <descrição curta> |

## 13. Condição para próxima etapa

- Status da revisão: `<draft ou validated>`
- Existem dúvidas bloqueantes: `<sim ou não>`
- Existem inconsistências não tratadas: `<sim ou não>`
- Artefato validado pelo usuário: `<sim ou não>`
- Pronto para handoff: `<sim ou não>`

## 14. Histórico de revisões

| Revisão | Data | Autor | Alteração |
|---|---|---|---|
| 1 | <data ou não informado> | Meeting Analyst | Criação inicial a partir das fontes informadas |