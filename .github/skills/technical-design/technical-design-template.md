# Template A — technical-design-index.md

---

artifact_type: technical-design-index
schema_version: "1.0"
work_item_id: "<work-item-id>"
title: "<título da demanda>"
status: "draft"
revision: 1
task_plan_baseline: "<caminho>"
task_plan_revision: "<revisão>"
repository: "<repositório ou não informado>"
created_by: "Technical Designer"
created_at: "<data/hora ou não informado>"
updated_at: "<data/hora ou não informado>"
validated_by: null
validated_at: null
------------------

# Índice dos desenhos técnicos — <título>

## 1. Situação

* Work item: `<work-item-id>`
* Status: `<draft | clarification-required | ready-for-validation | validated | stale>`
* Revisão: `<número>`
* Task plan: `<caminho e revisão>`
* Repositório: `<identificação>`
* Tarefas elegíveis: `<quantidade>`
* Desenhos validados: `<quantidade>`
* Desenhos prontos para código: `<quantidade>`
* Perguntas bloqueantes: `<quantidade>`

## 2. Baselines

| Artefato                | Caminho   | Status   |   Revisão | Utilização                    |
| ----------------------- | --------- | -------- | --------: | ----------------------------- |
| Requirements Analysis   | <caminho> | <status> | <revisão> | Comportamento e regras        |
| Business Solution Model | <caminho> | <status> | <revisão> | Fluxos, sistemas e fronteiras |
| Task Plan               | <caminho> | <status> | <revisão> | Tarefas e dependências        |

## 3. Tarefas e desenhos

| Tarefa   | Categoria           | Título   | Arquivo de desenho             | Status | Coding ready | Dependências |
| -------- | ------------------- | -------- | ------------------------------ | ------ | ------------ | ------------ |
| TASK-002 | BACKEND_DEVELOPMENT | <título> | `TASK-002-technical-design.md` | Draft  | Não          | <TASK-###>   |

## 4. Ordem recomendada

| Ordem | Tarefa   | Motivo   | Pode executar em paralelo |
| ----: | -------- | -------- | ------------------------- |
|     1 | TASK-002 | <motivo> | <TASK-### ou não>         |

## 5. Decisões técnicas compartilhadas

| ID         | Decisão   | Status                                      | Tarefas afetadas | Fonte   |
| ---------- | --------- | ------------------------------------------- | ---------------- | ------- |
| TD-DEC-001 | <decisão> | Proposed / Approved / Rejected / Superseded | <TASK-###>       | <fonte> |

## 6. Dependências compartilhadas

| ID         | Origem   | Relação    | Destino  | Motivo   |
| ---------- | -------- | ---------- | -------- | -------- |
| TD-DEP-001 | TASK-003 | blocked-by | TASK-002 | <motivo> |

## 7. Perguntas compartilhadas

| ID         | Status | Prioridade | Bloqueante | Pergunta   | Tarefas afetadas | Destino            |
| ---------- | ------ | ---------- | ---------- | ---------- | ---------------- | ------------------ |
| TD-QST-001 | Open   | P0         | Sim        | <pergunta> | <TASK-###>       | <equipe ou agente> |

## 8. Condição geral de handoff

* Todos os desenhos necessários foram criados: `<sim ou não>`
* Todas as perguntas P0 foram resolvidas: `<sim ou não>`
* Decisões compartilhadas foram aprovadas: `<sim ou não>`
* Dependências foram registradas: `<sim ou não>`
* Tarefas prontas para código: `<quantidade>`

## 9. Histórico

| Revisão | Data                    | Autor              | Alteração                 |
| ------: | ----------------------- | ------------------ | ------------------------- |
|       1 | <data ou não informada> | Technical Designer | Criação inicial do índice |

---

# Template B — `<task-id>-technical-design.md`

---

artifact_type: task-technical-design
schema_version: "1.0"
work_item_id: "<work-item-id>"
task_id: "<TASK-###>"
task_category: "<BACKEND_DEVELOPMENT | BACKEND_REPOSITORY_SETUP | FRONTEND_DEVELOPMENT>"
title: "<título da tarefa>"
status: "draft"
revision: 1
coding_ready: false
requirements_baseline: "<caminho>"
requirements_revision: "<revisão>"
solution_model_baseline: "<caminho>"
solution_model_revision: "<revisão>"
task_plan_baseline: "<caminho>"
task_plan_revision: "<revisão>"
repository: "<repositório>"
repository_branch: "<branch ou não informada>"
repository_commit: "<commit ou não informado>"
module: "<módulo ou não identificado>"
architecture_style: "<arquitetura observada>"
diagram_standard: "PlantUML"
diagram_files: []
created_by: "Technical Designer"
created_at: "<data/hora ou não informado>"
updated_at: "<data/hora ou não informado>"
validated_by: null
validated_at: null
------------------

# Desenho técnico — <TASK-###> — <título>

## 1. Situação do desenho

* Work item: `<work-item-id>`
* Tarefa: `<TASK-###>`
* Categoria: `<categoria>`
* Status: `<draft | clarification-required | ready-for-validation | validated | stale>`
* Revisão: `<número>`
* Repositório: `<repositório>`
* Branch ou commit analisado: `<identificação>`
* Perguntas abertas: `<quantidade>`
* Perguntas bloqueantes: `<quantidade>`
* Riscos críticos: `<quantidade>`
* Pronto para implementação: `<sim ou não>`

## 2. Contexto da tarefa

### Problema

<Problema que a tarefa ajuda a resolver.>

### Objetivo técnico

<Resultado técnico específico esperado.>

### História e critérios relacionados

* História: `<US-###>`
* Requisitos: `<FR-###, BR-###, INT-###, NFR-###>`
* Critérios de aceite: `<AC-###>`
* Fluxos: `<FLOW-###>`
* Sistemas: `<SYS-###>`

### Dentro do escopo

* <item>

### Fora do escopo

* <item>

## 3. Baselines e instruções utilizadas

| Fonte                   | Caminho   | Revisão ou versão         | Como foi utilizada     |
| ----------------------- | --------- | ------------------------- | ---------------------- |
| Requirements Analysis   | <caminho> | <revisão>                 | Regras e comportamento |
| Business Solution Model | <caminho> | <revisão>                 | Sistemas e fluxo       |
| Task Plan               | <caminho> | <revisão>                 | Escopo da tarefa       |
| Repository Instructions | <caminho> | <versão ou não informada> | Convenções             |
| ADR                     | <caminho> | <versão>                  | Decisão arquitetural   |

## 4. Baseline do repositório

| Item                  | Valor                       |
| --------------------- | --------------------------- |
| Linguagem             | <valor>                     |
| Runtime               | <valor>                     |
| Framework             | <valor>                     |
| Build                 | <valor>                     |
| Módulo                | <valor>                     |
| Arquitetura observada | <valor>                     |
| Framework de testes   | <valor>                     |
| Comandos de validação | <valor ou não identificado> |

## 5. Evidências do código existente

| ID       | Caminho     | Símbolo              | Tipo de referência | Relevância   |
| -------- | ----------- | -------------------- | ------------------ | ------------ |
| CODE-001 | `<caminho>` | `<classe ou método>` | Fluxo semelhante   | <explicação> |
| CODE-002 | `<caminho>` | `<classe ou método>` | Padrão de testes   | <explicação> |

Quando não existir referência equivalente:

`Nenhum fluxo equivalente foi localizado no repositório.`

## 6. Comportamento técnico atual

### Ponto de entrada atual

<Descrição ou não aplicável.>

### Fluxo atual

<Descrição objetiva sustentada pelo código.>

### Limitação ou problema atual

<Descrição.>

### Componentes atuais envolvidos

| Componente | Tipo                               | Caminho   | Responsabilidade   |
| ---------- | ---------------------------------- | --------- | ------------------ |
| <símbolo>  | <domínio, aplicação, adapter etc.> | <caminho> | <responsabilidade> |

## 7. Solução técnica proposta

### Visão geral

<Descrição da solução proposta.>

### Fluxo proposto

1. <passo>
2. <passo>
3. <passo>

### Resultado técnico esperado

<Resultado verificável.>

## 8. Mapeamento para arquitetura hexagonal

| ID       | Área               | Elemento   | Operação                   | Caminho atual ou proposto | Responsabilidade   | Requisitos |
| -------- | ------------------ | ---------- | -------------------------- | ------------------------- | ------------------ | ---------- |
| ARCH-001 | Domínio            | <elemento> | Create / Modify / Preserve | <caminho>                 | <responsabilidade> | <FR/BR>    |
| ARCH-002 | Aplicação          | <elemento> | Create / Modify / Preserve | <caminho>                 | <responsabilidade> | <FR/BR>    |
| ARCH-003 | Adapter de entrada | <elemento> | Create / Modify / Preserve | <caminho>                 | <responsabilidade> | <FR/INT>   |
| ARCH-004 | Port de saída      | <elemento> | Create / Modify / Preserve | <caminho>                 | <responsabilidade> | <INT>      |
| ARCH-005 | Adapter de saída   | <elemento> | Create / Modify / Preserve | <caminho>                 | <responsabilidade> | <INT>      |
| ARCH-006 | Composição         | <elemento> | Create / Modify / Preserve | <caminho>                 | <responsabilidade> | <fonte>    |

## 9. Impacto em arquivos

| ID       | Operação | Caminho              | Símbolo              | Alteração esperada | Motivo   | Risco           |
| -------- | -------- | -------------------- | -------------------- | ------------------ | -------- | --------------- |
| FILE-001 | Modify   | `<caminho>`          | `<símbolo>`          | <alteração>        | <motivo> | <risco>         |
| FILE-002 | Create   | `<caminho proposto>` | `<símbolo proposto>` | <criação>          | <motivo> | <risco>         |
| FILE-003 | Preserve | `<caminho>`          | `<símbolo>`          | Não alterar        | <motivo> | <risco evitado> |

Operações permitidas:

* `Create`
* `Modify`
* `Preserve`
* `Remove`
* `Candidate`

## 10. Contrato de entrada

| Item              | Definição                    | Status                            | Fonte ou pergunta |
| ----------------- | ---------------------------- | --------------------------------- | ----------------- |
| Tipo de entrada   | <HTTP, evento, job etc.>     | Confirmed / Proposed / To confirm | <fonte>           |
| Operação          | <método e rota, evento etc.> | <status>                          | <fonte>           |
| Autenticação      | <definição>                  | <status>                          | <fonte>           |
| Autorização       | <definição>                  | <status>                          | <fonte>           |
| Modelo de entrada | <modelo>                     | <status>                          | <fonte>           |
| Validações        | <validações>                 | <status>                          | <fonte>           |
| Respostas         | <respostas>                  | <status>                          | <fonte>           |
| Idempotência      | <definição>                  | <status>                          | <fonte>           |

## 11. Contratos de saída e integrações

| ID           | Port ou integração | Origem       | Destino   | Dados   | Sucesso     | Erros   | Estratégia                                |
| ------------ | ------------------ | ------------ | --------- | ------- | ----------- | ------- | ----------------------------------------- |
| TECH-INT-001 | <nome>             | <componente> | <sistema> | <dados> | <resultado> | <erros> | <timeout, retry, fallback ou a confirmar> |

## 12. Domínio e regras

| ID      | Regra ou conceito | Local proposto | Alteração   | Testes relacionados |
| ------- | ----------------- | -------------- | ----------- | ------------------- |
| DOM-001 | <regra>           | <elemento>     | <alteração> | <testes>            |

### Invariantes

* <invariante>

### Exceções de domínio

* <exceção>

## 13. Dados e persistência

### Impacto

`<Nenhum | Consulta | Inclusão | Alteração | Migration | Índice | Constraint>`

| ID       | Elemento                        | Operação   | Alteração   | Compatibilidade | Rollback     |
| -------- | ------------------------------- | ---------- | ----------- | --------------- | ------------ |
| DATA-001 | <tabela, entidade ou documento> | <operação> | <alteração> | <impacto>       | <estratégia> |

### Migration

* Necessária: `<sim ou não>`
* Tipo: `<aditiva, destrutiva ou não aplicável>`
* Estratégia: `<descrição>`
* Aprovação adicional necessária: `<sim ou não>`

## 14. Transação, concorrência e idempotência

* Boundary transacional: `<definição>`
* Concorrência relevante: `<sim ou não>`
* Risco de duplicidade: `<descrição>`
* Estratégia de idempotência: `<definição ou não aplicável>`
* Processamento parcial: `<comportamento>`
* Compensação: `<definição ou não aplicável>`

## 15. Configurações e ambientes

| ID      | Nome     | Tipo                          | Finalidade   | Obrigatória | Ambientes       | Sensível  | Status               |
| ------- | -------- | ----------------------------- | ------------ | ----------- | --------------- | --------- | -------------------- |
| CFG-001 | `<nome>` | Env / Property / Feature flag | <finalidade> | Sim / Não   | DEV / HML / PRD | Sim / Não | Confirmed / Proposed |

Não incluir valores secretos.

## 16. Segurança

* Autenticação: `<impacto>`
* Autorização: `<impacto>`
* Dados sensíveis: `<impacto>`
* Validação de entrada: `<impacto>`
* Logs sensíveis: `<tratamento>`
* Ameaças relevantes: `<descrição>`
* Revisão de segurança necessária: `<sim ou não>`

## 17. Tratamento de erros

| ID      | Condição   | Erro interno | Resposta ou comportamento externo | Log                | Retry                     |
| ------- | ---------- | ------------ | --------------------------------- | ------------------ | ------------------------- |
| ERR-001 | <condição> | <erro>       | <comportamento>                   | <nível e contexto> | <sim, não ou condicional> |

## 18. Observabilidade

| Categoria      | Definição             |
| -------------- | --------------------- |
| Logs           | <eventos e contexto>  |
| Métricas       | <métricas>            |
| Tracing        | <spans ou correlação> |
| Auditoria      | <eventos auditáveis>  |
| Alertas        | <condições>           |
| Correlation ID | <propagação>          |

## 19. Compatibilidade e implantação

* Compatibilidade com consumidores: `<descrição>`
* Mudança quebrável: `<sim ou não>`
* Versionamento necessário: `<sim ou não>`
* Feature flag: `<sim, não ou a confirmar>`
* Estratégia de rollout: `<descrição>`
* Estratégia de rollback: `<descrição>`
* Coexistência entre versões: `<descrição>`

## 20. Estratégia de testes automatizados

### Testes unitários

| Cenário   | Componente   | Resultado esperado |
| --------- | ------------ | ------------------ |
| <cenário> | <componente> | <resultado>        |

### Testes de integração

| Cenário   | Dependência   | Resultado esperado |
| --------- | ------------- | ------------------ |
| <cenário> | <dependência> | <resultado>        |

### Testes de contrato

| Cenário   | Contrato   | Resultado esperado |
| --------- | ---------- | ------------------ |
| <cenário> | <contrato> | <resultado>        |

### Testes de arquitetura

* <teste ou não aplicável>

### Regressões relevantes

* <teste existente que deve continuar passando>

### Comandos confirmados

```text
<comando encontrado nas instruções do projeto>
```

Não inventar comandos.

## 21. Sequência de implementação

| Ordem | Ação   | Arquivos ou elementos | Dependência   | Validação após o passo |
| ----: | ------ | --------------------- | ------------- | ---------------------- |
|     1 | <ação> | <elementos>           | <dependência> | <validação>            |
|     2 | <ação> | <elementos>           | <dependência> | <validação>            |

## 22. Diagramas

| ID         | Diagrama            | Aplicabilidade            | Arquivo PlantUML                         | Requisitos representados | Perguntas relacionadas |
| ---------- | ------------------- | ------------------------- | ---------------------------------------- | ------------------------ | ---------------------- |
| TD-DGM-001 | Componentes         | Aplicável / Não aplicável | `diagrams/<task-id>-components.puml`     | <FR/INT>                 | <TD-QST ou nenhuma>    |
| TD-DGM-002 | Sequência principal | Aplicável / Não aplicável | `diagrams/<task-id>-sequence-main.puml`  | <FR/BR/INT>              | <TD-QST ou nenhuma>    |
| TD-DGM-003 | Sequência de erro   | Aplicável / Não aplicável | `diagrams/<task-id>-sequence-error.puml` | <FR/BR>                  | <TD-QST ou nenhuma>    |
| TD-DGM-004 | Estados             | Aplicável / Não aplicável | `diagrams/<task-id>-state.puml`          | <FR/BR>                  | <TD-QST ou nenhuma>    |
| TD-DGM-005 | Dados               | Aplicável / Não aplicável | `diagrams/<task-id>-data-model.puml`     | <DATA/BR>                | <TD-QST ou nenhuma>    |
| TD-DGM-006 | Deployment          | Aplicável / Não aplicável | `diagrams/<task-id>-deployment.puml`     | <NFR/INT>                | <TD-QST ou nenhuma>    |

## 23. Alternativas técnicas

### TD-OPT-001 — <nome>

* Status: `<Candidate | Selected | Rejected>`
* Descrição: <descrição>
* Aderência ao projeto: <avaliação>
* Benefícios:

    * <benefício>
* Desvantagens:

    * <desvantagem>
* Riscos:

    * <risco>
* Impacto:

    * <impacto>
* Recomendação:

    * <recomendação>
* Responsável pela decisão:

    * <pessoa ou equipe>

## 24. Decisões técnicas

| ID         | Decisão   | Status                                      | Justificativa   | Aprovada por       | Elementos impactados               |
| ---------- | --------- | ------------------------------------------- | --------------- | ------------------ | ---------------------------------- |
| TD-DEC-001 | <decisão> | Proposed / Approved / Rejected / Superseded | <justificativa> | <pessoa ou equipe> | <arquivos, contratos ou diagramas> |

## 25. Perguntas técnicas

| ID         | Status | Prioridade | Bloqueante | Categoria | Pergunta   | Impacto   | Destino            |
| ---------- | ------ | ---------- | ---------- | --------- | ---------- | --------- | ------------------ |
| TD-QST-001 | Open   | P0         | Sim        | Contrato  | <pergunta> | <impacto> | <agente ou equipe> |

Prioridades:

* `P0`: impede implementação segura;
* `P1`: pode alterar significativamente o desenho;
* `P2`: melhora qualidade ou precisão;
* `P3`: detalhe não bloqueante.

## 26. Riscos

| ID          | Risco   | Probabilidade        | Impacto              | Mitigação   | Responsável |
| ----------- | ------- | -------------------- | -------------------- | ----------- | ----------- |
| TD-RISK-001 | <risco> | Alta / Média / Baixa | Alto / Médio / Baixo | <mitigação> | <papel>     |

## 27. Contrato para o Coding Agent

### Objetivo

<Resultado que o Coding Agent deve implementar.>

### Arquivos permitidos

* `<caminho>`
* `<caminho proposto>`

### Arquivos que não devem ser alterados

* `<caminho>`
* `<área fora do escopo>`

### Alterações esperadas

* <alteração>
* <alteração>

### Decisões obrigatórias

* `<TD-DEC-###>`

### Testes obrigatórios

* <teste>
* <teste>

### Comandos obrigatórios

```text
<comandos confirmados>
```

### Evidências esperadas

* diff restrito ao escopo;
* testes executados;
* resultado dos comandos;
* justificativa para desvios;
* indicação de arquivos adicionais necessários.

### Condições de parada

O Coding Agent deve interromper e solicitar decisão quando:

* um requisito contradizer o código ou outra baseline;
* for necessário alterar arquivo fora do escopo;
* for necessária uma dependência não aprovada;
* surgir migration destrutiva;
* o contrato externo estiver indefinido;
* um teste falhar por motivo não relacionado;
* o desenho precisar ser modificado;
* houver risco de segurança não previsto.

## 28. Verificação final

* [ ] A tarefa está corretamente identificada
* [ ] As baselines foram registradas
* [ ] As instruções do projeto foram consideradas
* [ ] O código existente foi pesquisado
* [ ] Referências reais possuem caminhos
* [ ] Elementos propostos estão identificados como propostas
* [ ] Arquivos impactados foram listados
* [ ] O desenho respeita a arquitetura real do projeto
* [ ] Contratos foram avaliados
* [ ] Dados e migrations foram avaliados
* [ ] Integrações foram avaliadas
* [ ] Segurança foi avaliada
* [ ] Erros foram avaliados
* [ ] Configurações foram avaliadas
* [ ] Observabilidade foi avaliada
* [ ] Compatibilidade foi avaliada
* [ ] Estratégia de testes está definida
* [ ] Comandos possuem fonte
* [ ] Sequência de implementação está definida
* [ ] Diagramas aplicáveis foram produzidos
* [ ] Perguntas P0 foram resolvidas
* [ ] Riscos críticos possuem mitigação
* [ ] Contrato para o Coding Agent está completo
* [ ] Nenhum código foi alterado

## 29. Condição para implementação

* Baselines validadas: `<sim ou não>`
* Task plan validado: `<sim ou não>`
* Escopo técnico definido: `<sim ou não>`
* Arquivos impactados identificados: `<sim ou não>`
* Contratos definidos: `<sim ou não>`
* Testes definidos: `<sim ou não>`
* Perguntas P0 abertas: `<quantidade>`
* Riscos críticos sem tratamento: `<quantidade>`
* Desenho aprovado pelo usuário: `<sim ou não>`
* Coding ready: `<sim ou não>`

### Bloqueios

* <TD-QST-###, TD-RISK-### ou nenhum bloqueio>

## 30. Histórico de revisões

| Revisão | Data                    | Autor              | Alteração                          |
| ------: | ----------------------- | ------------------ | ---------------------------------- |
|       1 | <data ou não informada> | Technical Designer | Criação inicial do desenho técnico |
