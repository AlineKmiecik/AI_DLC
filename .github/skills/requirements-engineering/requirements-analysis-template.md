---

artifact_type: requirements-analysis
schema_version: "1.0"
work_item_id: "<work-item-id>"
title: "<título da demanda>"
status: "draft"
revision: 1
handoff_ready: false
project: "<projeto ou não informado>"
related_systems: []
source_files: []
created_by: "Requirements Engineer"
created_at: "<data/hora ou não informado>"
updated_at: "<data/hora ou não informado>"
validated_by: null
validated_at: null
------------------

# Requisitos — <título da demanda>

## 1. Situação da análise

* Work item: `<work-item-id>`
* Status: `<draft | clarification-required | ready-for-validation | validated>`
* Revisão: `<número>`
* Perguntas abertas: `<quantidade>`
* Perguntas bloqueantes: `<quantidade>`
* Conflitos abertos: `<quantidade>`
* Pronto para handoff: `<sim ou não>`

## 2. Resumo da demanda

### Problema

<Problema que motivou a demanda.>

### Objetivo

<Resultado de negócio esperado.>

### Resultado de sucesso

<Como o sucesso será percebido ou medido, quando conhecido.>

### Contexto consolidado

<Contexto necessário para compreender a demanda sem reproduzir todas
as reuniões.>

## 3. Inventário das fontes

| ID      | Fonte             | Tipo   | Status   | Autoridade             | Escopo coberto | Observações  |
| ------- | ----------------- | ------ | -------- | ---------------------- | -------------- | ------------ |
| SRC-001 | <caminho ou nome> | <tipo> | <status> | <alta, média ou baixa> | <assunto>      | <observação> |

## 4. Atores e partes interessadas

| ID        | Ator, equipe ou sistema | Papel na demanda | Responsabilidades ou interesses | Fonte   |
| --------- | ----------------------- | ---------------- | ------------------------------- | ------- |
| ACTOR-001 | <ator>                  | <papel>          | <responsabilidade>              | <fonte> |

## 5. Glossário

| Termo   | Definição   | Sinônimos ou variações | Fonte   | Situação                 |
| ------- | ----------- | ---------------------- | ------- | ------------------------ |
| <termo> | <definição> | <variações>            | <fonte> | Confirmado / A confirmar |

## 6. Escopo

### Incluído

* <item confirmado ou candidato>

### Fora do escopo

* <item explicitamente excluído>

### Limites ainda não definidos

* <limite relacionado a uma pergunta aberta>

## 7. Requisitos funcionais

| ID     | Requisito           | Status                                        | Prioridade                            | Fontes    | Perguntas relacionadas |
| ------ | ------------------- | --------------------------------------------- | ------------------------------------- | --------- | ---------------------- |
| FR-001 | <O sistema deve...> | Candidate / Confirmed / Superseded / Rejected | <Must, Should, Could ou não definida> | <SRC-###> | <QST-### ou nenhuma>   |

## 8. Regras de negócio

| ID     | Regra               | Status                                        | Fontes    | Exceções                      | Perguntas relacionadas |
| ------ | ------------------- | --------------------------------------------- | --------- | ----------------------------- | ---------------------- |
| BR-001 | <regra declarativa> | Candidate / Confirmed / Superseded / Rejected | <SRC-###> | <exceção ou não identificada> | <QST-###>              |

## 9. Requisitos de dados

| ID       | Dado ou conjunto de dados | Necessidade   | Origem   | Validação ou restrição | Status                | Fontes    |
| -------- | ------------------------- | ------------- | -------- | ---------------------- | --------------------- | --------- |
| DATA-001 | <dado>                    | <necessidade> | <origem> | <validação>            | Candidate / Confirmed | <SRC-###> |

## 10. Requisitos de integração

| ID      | Sistemas envolvidos | Necessidade   | Dados ou evento   | Comportamento de sucesso | Comportamento de falha | Status                | Fontes    |
| ------- | ------------------- | ------------- | ----------------- | ------------------------ | ---------------------- | --------------------- | --------- |
| INT-001 | <origem e destino>  | <necessidade> | <dados ou evento> | <sucesso>                | <falha ou pergunta>    | Candidate / Confirmed | <SRC-###> |

## 11. Requisitos não funcionais

| ID      | Categoria                               | Requisito   | Métrica ou condição verificável | Status                | Fontes    | Perguntas relacionadas |
| ------- | --------------------------------------- | ----------- | ------------------------------- | --------------------- | --------- | ---------------------- |
| NFR-001 | <desempenho, segurança, auditoria etc.> | <requisito> | <métrica ou não definida>       | Candidate / Confirmed | <SRC-###> | <QST-###>              |

## 12. Histórias de usuário

### US-001 — <título>

* Status: `<Draft | Ready | Superseded | Rejected>`
* Ator: `<ator>`
* Requisitos relacionados: `<FR-###, BR-###, NFR-###>`
* Fontes: `<SRC-###>`
* Perguntas bloqueantes: `<QST-### ou nenhuma>`

**História**

Como `<ator>`, quero `<capacidade>`, para `<benefício>`.

**Critérios de aceite**

#### AC-001 — <título do cenário>

Dado que `<contexto ou estado inicial>`

Quando `<ação ou evento>`

Então `<resultado observável>`

#### AC-002 — <título do cenário>

Dado que `<contexto ou estado inicial>`

Quando `<ação ou evento>`

Então `<resultado observável>`

## 13. Registro de perguntas

| ID      | Status | Prioridade | Bloqueante | Categoria   | Pergunta           | Motivo e impacto                  | Itens afetados | Quem pode responder | Resposta e evidência |
| ------- | ------ | ---------- | ---------- | ----------- | ------------------ | --------------------------------- | -------------- | ------------------- | -------------------- |
| QST-001 | Open   | P0         | Sim        | <categoria> | <pergunta atômica> | <por que a resposta é necessária> | <FR/BR/US/AC>  | <pessoa ou equipe>  | Não respondida       |

Status permitidos:

* `Open`
* `Partially answered`
* `Answered`
* `Resolved`
* `Cancelled`

## 14. Conflitos entre fontes

| ID      | Descrição  | Fontes envolvidas   | Impacto   | Itens afetados | Pergunta de resolução | Status                     |
| ------- | ---------- | ------------------- | --------- | -------------- | --------------------- | -------------------------- |
| CNF-001 | <conflito> | <SRC-### e SRC-###> | <impacto> | <itens>        | <QST-###>             | Open / Resolved / Accepted |

## 15. Hipóteses

| ID      | Hipótese   | Motivo   | Evidência disponível  | Risco   | Pergunta relacionada |
| ------- | ---------- | -------- | --------------------- | ------- | -------------------- |
| HYP-001 | <hipótese> | <motivo> | <fonte ou observação> | <risco> | <QST-###>            |

Hipóteses não são requisitos confirmados.

## 16. Decisões e respostas incorporadas

| ID      | Decisão ou resposta   | Respondida ou aprovada por | Fonte   | Data                    | Itens atualizados |
| ------- | --------------------- | -------------------------- | ------- | ----------------------- | ----------------- |
| DEC-001 | <decisão ou resposta> | <pessoa ou equipe>         | <fonte> | <data ou não informada> | <FR/BR/US/AC/QST> |

## 17. Matriz de rastreabilidade

| Item   | Fontes           | Perguntas | História relacionada | Critérios de aceite |
| ------ | ---------------- | --------- | -------------------- | ------------------- |
| FR-001 | SRC-001, SRC-002 | QST-001   | US-001               | AC-001, AC-002      |

## 18. Condição para próxima etapa

* Fontes essenciais validadas: `<sim ou não>`
* Perguntas P0 abertas: `<quantidade>`
* Perguntas P1 abertas: `<quantidade>`
* Conflitos críticos abertos: `<quantidade>`
* Requisitos principais possuem fontes: `<sim ou não>`
* Histórias principais possuem critérios verificáveis: `<sim ou não>`
* Artefato aprovado pelo usuário: `<sim ou não>`
* Pronto para handoff: `<sim ou não>`

### Bloqueios para o handoff

* <QST-###, CNF-### ou nenhum bloqueio>

### Observações para a próxima etapa

* <informação relevante para o Business and Solution Modeler>

## 19. Histórico de revisões

| Revisão | Data                    | Autor                 | Alteração                               |
| ------- | ----------------------- | --------------------- | --------------------------------------- |
| 1       | <data ou não informada> | Requirements Engineer | Criação inicial do dossiê de requisitos |
