---

artifact_type: task-plan
schema_version: "1.1"
work_item_id: "<work-item-id>"
title: "<título da demanda>"
status: "draft"
revision: 1
jira_ready: false
handoff_ready: false
requirements_baseline: "<caminho do requirements-analysis.md>"
requirements_baseline_status: "<status>"
requirements_baseline_revision: "<revisão>"
solution_model_baseline: "<caminho do business-solution-model.md>"
solution_model_baseline_status: "<status>"
solution_model_baseline_revision: "<revisão>"
project: "<projeto ou não informado>"
xray_project: "<projeto ou não informado>"
confluence_space: "<espaço ou não informado>"
homologation_environment: "<identificação ou não informada>"
homologation_swagger_url: "<URL ou não informada>"
created_by: "Task Planner"
created_at: "<data/hora ou não informado>"
updated_at: "<data/hora ou não informado>"
validated_by: null
validated_at: null
------------------

# Plano de tarefas — <título da demanda>

## 1. Situação do planejamento

* Work item: `<work-item-id>`
* Status: `<draft | clarification-required | ready-for-validation | validated>`
* Revisão: `<número>`
* Histórias planejadas: `<quantidade>`
* Tarefas backend: `<quantidade>`
* Tarefas frontend: `<quantidade>`
* Perguntas abertas: `<quantidade>`
* Perguntas bloqueantes: `<quantidade>`
* Pronto para Jira: `<sim ou não>`
* Pronto para Technical Designer: `<sim ou não>`

## 2. Baselines utilizadas

| Artefato                    | Caminho   | Status   |   Revisão | Pronto para handoff |
| --------------------------- | --------- | -------- | --------: | ------------------- |
| Requirements Analysis       | <caminho> | <status> | <revisão> | Sim / Não           |
| Business and Solution Model | <caminho> | <status> | <revisão> | Sim / Não           |

## 3. Contexto operacional

| Item                             | Valor               | Situação                 |
| -------------------------------- | ------------------- | ------------------------ |
| Projeto Jira                     | <projeto>           | Confirmado / A confirmar |
| Projeto ou organização Xray      | <projeto>           | Confirmado / A confirmar |
| Ambiente de homologação          | <ambiente>          | Confirmado / A confirmar |
| Swagger de homologação           | <URL>               | Confirmado / A confirmar |
| Espaço do Confluence             | <espaço>            | Confirmado / A confirmar |
| Página existente no Confluence   | <URL ou não existe> | Confirmado / A confirmar |
| Papel responsável pela validação | <papel>             | Confirmado / A confirmar |

## 4. Resumo da demanda

### Problema

<Problema resumido.>

### Objetivo

<Resultado esperado.>

### Sistemas e equipes envolvidos

* <sistema ou equipe>

### Restrições relevantes

* <restrição>

### Fora do escopo

* <item>

## 5. Classificação das histórias

| História | Título   | Classificação                                             | Sistemas  | Equipes   | Status                | Justificativa |
| -------- | -------- | --------------------------------------------------------- | --------- | --------- | --------------------- | ------------- |
| US-001   | <título> | Backend / Frontend / Full stack / Classification required | <SYS-###> | <equipes> | Confirmed / Candidate | <motivo>      |

## 6. Resumo das tarefas por história

| História | Repo setup | Xray design | Dev backend | Xray HML | Validação HML | Confluence | Dev frontend | Total | Política válida |
| -------- | ---------: | ----------: | ----------: | -------: | ------------: | ---------: | -----------: | ----: | --------------- |
| US-001   |          0 |           1 |           2 |        1 |             1 |          1 |            0 |     6 | Sim             |

Regras:

* repositório: somente quando confirmado;
* Xray Design: uma tarefa backend;
* desenvolvimento backend: uma a três tarefas;
* Xray HML: uma tarefa backend;
* validação HML: uma tarefa backend independente;
* Confluence: uma tarefa backend;
* frontend: uma a três tarefas de desenvolvimento, sem outras quebras
  automáticas.

## 7. Decisões de decomposição

| ID      | História | Decisão                                          | Justificativa                                        | Fonte         |
| ------- | -------- | ------------------------------------------------ | ---------------------------------------------------- | ------------- |
| TPD-001 | US-001   | Utilizar duas tarefas de desenvolvimento backend | <motivo funcional>                                   | <FR/FLOW/SYS> |
| TPD-002 | US-001   | Não criar novo repositório                       | A solução será implementada no repositório existente | <fonte>       |

## 8. Índice das tarefas

| ID       | Título   | Categoria   | História pai | Status   | Executor recomendado | Independência | Dependências          |
| -------- | -------- | ----------- | ------------ | -------- | -------------------- | ------------- | --------------------- |
| TASK-001 | <título> | <categoria> | US-001       | Proposed | <papel>              | <regra>       | <TASK-### ou nenhuma> |

Categorias permitidas:

* `BACKEND_REPOSITORY_SETUP`
* `BACKEND_XRAY_TEST_DESIGN`
* `BACKEND_DEVELOPMENT`
* `BACKEND_XRAY_TEST_EXECUTION_HML`
* `BACKEND_HML_FUNCTIONAL_VALIDATION`
* `BACKEND_CONFLUENCE_DOCUMENTATION`
* `FRONTEND_DEVELOPMENT`

## 9. Detalhamento das tarefas

Repita a estrutura abaixo para cada tarefa.

---

### TASK-001 — <título orientado a resultado>

* Categoria: `<categoria>`
* História pai: `<US-###>`
* Status: `<Proposed | Approved | Superseded | Cancelled>`
* Equipe: `<Backend | Frontend | QA | Funcional | Plataforma>`
* Executor recomendado: `<papel>`
* Restrição de independência: `<não aplicável | preferencialmente diferente do desenvolvedor | deve ser diferente do desenvolvedor>`
* Ordem sugerida: `<número ou paralela>`
* Dependências: `<TASK-###, sistema, ambiente ou nenhuma>`
* Pode executar em paralelo com: `<TASK-### ou nenhuma>`
* Requisitos relacionados: `<FR-###, BR-###, INT-###, NFR-###>`
* Critérios de aceite relacionados: `<AC-###>`
* Fluxos e sistemas relacionados: `<FLOW-###, SYS-###, INT-###>`

#### Descrição para o Jira

##### Contexto

<Explique o problema, o ator, o fluxo, a história e a razão desta tarefa.>

##### Objetivo

<Defina o resultado específico da tarefa.>

##### Escopo

* <item incluído>
* <item incluído>
* <regra, cenário ou artefato incluído>

##### Atividade ou comportamento esperado

<Descreva o que deve ser feito e o resultado esperado.>

##### Restrições e decisões aprovadas

* <decisão confirmada>
* <restrição confirmada>

Quando aplicável:

`Os componentes, arquivos e detalhes internos serão definidos pelo
Technical Designer.`

##### Entregáveis

* <resultado concreto>
* <artefato>
* <vínculo no Jira, Xray ou Confluence>

##### Evidências e definição de pronto

* [ ] Atividade concluída
* [ ] História e critérios relacionados atendidos
* [ ] Evidências registradas
* [ ] Links e referências registrados
* [ ] Dependências atualizadas
* [ ] Nenhuma alteração fora do escopo

##### Dependências e pré-requisitos

* <tarefa, ambiente, acesso, decisão ou dado>

##### Executor e independência

* Papel recomendado: `<papel>`
* Pode ser o desenvolvedor principal: `<sim ou não>`
* Exceção permitida: `<condição ou não aplicável>`

##### Fora do escopo

* <item>

##### Referências

* História: `<US-###>`
* Requisitos: `<FR/BR/INT/NFR>`
* Critérios: `<AC-###>`
* Fluxos: `<FLOW-###>`
* Sistemas: `<SYS-###>`
* Fontes: `<SRC-###>`

---

## 10. Conteúdo específico das tarefas Xray

### TASK-<ID> — Xray Test Design

* Projeto Xray: `<identificação ou a confirmar>`
* História Jira vinculada: `<US/Jira issue>`
* Critérios cobertos: `<AC-###>`
* Testes novos: `<quantidade ou a definir>`
* Testes existentes a atualizar: `<IDs ou nenhum>`
* Pré-condições necessárias: `<descrição>`
* Dados necessários: `<descrição>`

#### Definição de pronto Xray Design

* [ ] Testes criados ou atualizados no Xray
* [ ] Testes vinculados à história
* [ ] Pré-condições registradas
* [ ] Passos e resultados esperados registrados
* [ ] Cenários positivos cobertos
* [ ] Cenários negativos cobertos
* [ ] Limites e exceções cobertos
* [ ] Critérios de aceite rastreados
* [ ] Cenários revisados

### TASK-<ID> — Xray Test Execution HML

* Ambiente: `Homologação`
* Versão ou build: `<identificação>`
* Execução Xray: `<ID ou a criar>`
* Testes vinculados: `<IDs>`
* Executor recomendado: `<QA, analista ou outro desenvolvedor>`
* Independência: `Preferencialmente diferente do desenvolvedor principal`

#### Definição de pronto Xray Execution

* [ ] Versão disponível em homologação
* [ ] Execução criada ou atualizada no Xray
* [ ] Todos os testes aplicáveis executados
* [ ] Resultado real registrado
* [ ] Evidências anexadas
* [ ] Dados de teste registrados
* [ ] Defeitos vinculados quando houver
* [ ] Reexecuções registradas
* [ ] Resultado final rastreável

## 11. Validação funcional em homologação

### TASK-<ID> — Functional Validation HML

* Ambiente: `Homologação`
* Versão ou build: `<identificação>`
* Executor recomendado: `<QA, analista funcional, produto ou outro desenvolvedor>`
* Independência: `Deve ser diferente do desenvolvedor principal`
* Execução Xray relacionada: `<ID>`
* História e critérios: `<US/AC>`

#### Escopo da validação

* fluxo principal;
* critérios de aceite;
* cenários alternativos relevantes;
* integrações;
* respostas de erro;
* resultado percebido pelo consumidor;
* regressões funcionais relevantes.

#### Definição de pronto da validação

* [ ] Validação realizada por pessoa independente
* [ ] Versão validada registrada
* [ ] Critérios de aceite revisados
* [ ] Execução Xray referenciada
* [ ] Evidências registradas
* [ ] Resultado classificado como aprovado, aprovado com ressalvas ou reprovado
* [ ] Ressalvas e defeitos documentados
* [ ] Aprovação ou reprovação registrada no Jira

## 12. Documentação no Confluence

### TASK-<ID> — Confluence Documentation

* Espaço: `<espaço>`
* Página existente: `<URL ou não existe>`
* Página a criar ou atualizar: `<título>`
* Público: `<equipes consumidoras, novos desenvolvedores, suporte etc.>`
* Swagger de homologação: `<URL>`
* Rota específica: `<método e caminho>`
* Diagrama de sequência: `<novo ou existente>`

#### Conteúdo esperado

* [ ] Objetivo e contexto
* [ ] Escopo e fora do escopo
* [ ] Atores e sistemas
* [ ] Visão geral do fluxo
* [ ] Pré-condições
* [ ] Autenticação e autorização
* [ ] Método e rota
* [ ] Headers
* [ ] Path e query parameters
* [ ] Objeto de entrada
* [ ] Campos obrigatórios e opcionais
* [ ] Exemplo de requisição
* [ ] Objeto de saída
* [ ] Exemplo de resposta de sucesso
* [ ] Códigos e tipos de resposta
* [ ] Estruturas e mensagens de erro
* [ ] Condição que produz cada resposta
* [ ] Integrações e dependências
* [ ] Limitações conhecidas
* [ ] Diagrama de sequência
* [ ] Fonte PlantUML do diagrama, quando aplicável
* [ ] Link do Swagger de homologação
* [ ] Link direto ou orientação para localizar a rota
* [ ] Link da história do Jira
* [ ] Links dos testes e execução no Xray
* [ ] Equipe mantenedora
* [ ] Versão ou data da atualização

#### Definição de pronto da documentação

* [ ] Página criada ou atualizada no Confluence
* [ ] Conteúdo revisado contra o comportamento validado em homologação
* [ ] Swagger de homologação acessível
* [ ] Rota específica identificável
* [ ] Respostas e erros documentados
* [ ] Diagrama de sequência incluído
* [ ] Links Jira e Xray incluídos
* [ ] Nenhum segredo ou credencial exposto
* [ ] Página revisada por outro integrante da equipe

## 13. Cobertura da política

### US-001 — <título>

* Classificação: `<Backend | Frontend | Full stack>`
* Novo repositório necessário: `<Sim | Não | A confirmar>`
* Novo repositório confirmado por: `<fonte ou não aplicável>`
* Tarefas backend de desenvolvimento: `<0–3>`
* Tarefas frontend de desenvolvimento: `<0–3>`

| Verificação                 |                          Esperado | Encontrado | Resultado               |
| --------------------------- | --------------------------------: | ---------: | ----------------------- |
| Repo setup                  | 0 ou 1 por repositório confirmado |   <número> | Conforme / Não conforme |
| Xray Test Design            |           1 quando houver backend |   <número> | Conforme / Não conforme |
| Desenvolvimento backend     |         1–3 quando houver backend |   <número> | Conforme / Não conforme |
| Xray Test Execution HML     |           1 quando houver backend |   <número> | Conforme / Não conforme |
| Validação funcional HML     |           1 quando houver backend |   <número> | Conforme / Não conforme |
| Documentação Confluence     |           1 quando houver backend |   <número> | Conforme / Não conforme |
| Desenvolvimento frontend    |        1–3 quando houver frontend |   <número> | Conforme / Não conforme |
| Quebras adicionais frontend |                                 0 |   <número> | Conforme / Não conforme |

## 14. Dependências

| ID      | Origem   | Relação    | Destino  | Motivo                                                      | Impacto                                     |
| ------- | -------- | ---------- | -------- | ----------------------------------------------------------- | ------------------------------------------- |
| DEP-001 | TASK-004 | blocked-by | TASK-003 | A versão precisa estar disponível em homologação            | Testes não podem ser executados             |
| DEP-002 | TASK-005 | blocked-by | TASK-004 | A validação utiliza a execução do Xray                      | Aprovação funcional indisponível            |
| DEP-003 | TASK-006 | blocked-by | TASK-005 | A documentação final deve refletir o comportamento validado | Risco de documentar comportamento incorreto |

Relações permitidas:

* `blocks`
* `blocked-by`
* `can-run-in-parallel`
* `requires-input-from`
* `requires-environment`
* `requires-approval`

## 15. Matriz de independência

| História | Tarefas de desenvolvimento | Execução Xray | Validação funcional | Independência atendida  | Exceção                   |
| -------- | -------------------------- | ------------- | ------------------- | ----------------------- | ------------------------- |
| US-001   | TASK-002, TASK-003         | TASK-004      | TASK-005            | Sim / Não / A confirmar | <motivo ou não aplicável> |

## 16. Perguntas de planejamento

| ID         | Status | Prioridade | Bloqueante | Pergunta                                                             | Motivo e impacto                        | Itens afetados | Quem pode responder | Destino              |
| ---------- | ------ | ---------- | ---------- | -------------------------------------------------------------------- | --------------------------------------- | -------------- | ------------------- | -------------------- |
| TP-QST-001 | Open   | P1         | Não        | Qual pessoa ou papel realizará a validação funcional em homologação? | Necessário para garantir independência  | TASK-005       | <equipe>            | Gestão / QA          |
| TP-QST-002 | Open   | P1         | Não        | Já existe uma página no Confluence para este fluxo?                  | Evita documentação duplicada            | TASK-006       | <equipe>            | Backend              |
| TP-QST-003 | Open   | P1         | Sim        | Qual é a URL do Swagger de homologação?                              | Necessário para concluir a documentação | TASK-006       | <equipe>            | Backend / Plataforma |

## 17. Assuntos para o Technical Designer

| ID             | Tarefa   | Assunto técnico pendente                                 | Impacto                            | Bloqueia o planejamento |
| -------------- | -------- | -------------------------------------------------------- | ---------------------------------- | ----------------------- |
| TD-HANDOFF-001 | TASK-002 | Definir componentes e arquivos que implementarão o fluxo | Interno à implementação            | Não                     |
| TD-HANDOFF-002 | TASK-006 | Definir participantes técnicos do diagrama de sequência  | Necessário para documentação final | Não                     |

## 18. Verificação final

| Verificação                                      | Resultado | Observação   |
| ------------------------------------------------ | --------- | ------------ |
| Histórias classificadas                          | Sim / Não | <observação> |
| Repo setup criado somente quando necessário      | Sim / Não | <observação> |
| Testes funcionais vinculados ao Xray             | Sim / Não | <observação> |
| Execução planejada em homologação                | Sim / Não | <observação> |
| Evidências de execução exigidas                  | Sim / Não | <observação> |
| Validação funcional independente                 | Sim / Não | <observação> |
| Existem de uma a três tarefas de desenvolvimento | Sim / Não | <observação> |
| Não existem tarefas separadas apenas por camada  | Sim / Não | <observação> |
| Testes automatizados aparecem no desenvolvimento | Sim / Não | <observação> |
| Documentação prevista no Confluence              | Sim / Não | <observação> |
| Swagger de homologação previsto                  | Sim / Não | <observação> |
| Respostas e erros previstos na documentação      | Sim / Não | <observação> |
| Diagrama de sequência previsto                   | Sim / Não | <observação> |
| Dependências registradas                         | Sim / Não | <observação> |
| Perguntas P0 resolvidas                          | Sim / Não | <observação> |
| Plano pronto para Jira                           | Sim / Não | <observação> |
| Plano pronto para Technical Designer             | Sim / Não | <observação> |

## 19. Condição para próxima etapa

* Baseline de requisitos validada: `<sim ou não>`
* Modelo de solução validado: `<sim ou não>`
* Histórias classificadas: `<sim ou não>`
* Tarefas obrigatórias presentes: `<sim ou não>`
* Tarefas condicionais justificadas: `<sim ou não>`
* Execução em homologação definida: `<sim ou não>`
* Independência da validação definida: `<sim ou não>`
* Documentação Confluence definida: `<sim ou não>`
* Perguntas P0 abertas: `<quantidade>`
* Descrições completas: `<sim ou não>`
* Artefato aprovado pelo usuário: `<sim ou não>`
* Jira ready: `<sim ou não>`
* Handoff ready: `<sim ou não>`

### Bloqueios para Jira

* <TP-QST-### ou nenhum bloqueio>

### Bloqueios para Technical Designer

* <TP-QST-### ou nenhum bloqueio>

## 20. Histórico de revisões

| Revisão | Data                    | Autor        | Alteração                |
| ------- | ----------------------- | ------------ | ------------------------ |
| 1       | <data ou não informada> | Task Planner | Criação inicial do plano |
