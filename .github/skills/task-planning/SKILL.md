---

name: task-planning
description: Metodologia para decompor histórias em tarefas Jira-ready. Para backend, planeja testes funcionais no Xray, uma a três tarefas de desenvolvimento, execução no Xray em homologação, validação funcional independente em homologação e documentação no Confluence. A criação de repositório é condicional. Para frontend, cria somente uma a três tarefas de desenvolvimento.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Objetivo

Transformar histórias e modelos de solução em tarefas:

* compreensíveis;
* executáveis;
* rastreáveis;
* contextualizadas;
* compatíveis com Jira e Xray;
* sem fragmentação excessiva;
* prontas para revisão humana.

Esta skill planeja o trabalho.

Ela não executa, publica ou implementa o trabalho.

# Artefato obrigatório

Utilize:

`task-plan-template.md`

Produza ou atualize:

`docs/ai-dlc/work-items/<work-item-id>/task-plan.md`

Quando o usuário indicar outro caminho, utilize-o.

# Fontes principais

Utilize:

1. `requirements-analysis.md`;
2. `business-solution-model.md`.

Extraia:

* histórias;
* requisitos;
* critérios de aceite;
* regras;
* atores;
* capacidades;
* fluxos;
* sistemas;
* integrações;
* dependências;
* impactos;
* perguntas abertas.

Não copie integralmente as baselines.

Utilize referências como:

* `US-001`;
* `FR-002`;
* `BR-004`;
* `AC-006`;
* `FLOW-001`;
* `SYS-002`;
* `INT-003`.

# Catálogo de categorias

Utilize:

* `BACKEND_REPOSITORY_SETUP`
* `BACKEND_XRAY_TEST_DESIGN`
* `BACKEND_DEVELOPMENT`
* `BACKEND_XRAY_TEST_EXECUTION_HML`
* `BACKEND_HML_FUNCTIONAL_VALIDATION`
* `BACKEND_CONFLUENCE_DOCUMENTATION`
* `FRONTEND_DEVELOPMENT`

# Política de backend

Para cada história backend:

| Categoria                           | Mínimo |                 Máximo | Regra                  |
| ----------------------------------- | -----: | ---------------------: | ---------------------- |
| `BACKEND_REPOSITORY_SETUP`          |      0 | 1 por novo repositório | Condicional            |
| `BACKEND_XRAY_TEST_DESIGN`          |      1 |                      1 | Obrigatória por padrão |
| `BACKEND_DEVELOPMENT`               |      1 |                      3 | Obrigatória            |
| `BACKEND_XRAY_TEST_EXECUTION_HML`   |      1 |                      1 | Obrigatória por padrão |
| `BACKEND_HML_FUNCTIONAL_VALIDATION` |      1 |                      1 | Obrigatória por padrão |
| `BACKEND_CONFLUENCE_DOCUMENTATION`  |      1 |                      1 | Obrigatória por padrão |

A quantidade padrão será:

* cinco tarefas com uma tarefa de desenvolvimento;
* seis tarefas com duas tarefas de desenvolvimento;
* sete tarefas com três tarefas de desenvolvimento;
* mais uma tarefa para cada novo repositório confirmado.

Uma tarefa obrigatória somente pode ser omitida mediante decisão explícita,
justificada e registrada.

# Política de frontend

Para cada história frontend:

| Categoria              | Mínimo | Máximo |
| ---------------------- | -----: | -----: |
| `FRONTEND_DEVELOPMENT` |      1 |      3 |

Não gere automaticamente outras categorias para frontend.

# Novo repositório

Antes de criar `BACKEND_REPOSITORY_SETUP`, verifique:

* existe decisão explícita?
* existe novo serviço ou aplicação?
* o repositório atual não será utilizado?
* o usuário confirmou a criação?
* existe nome ou finalidade conhecida?

Quando a resposta não estiver confirmada:

1. crie uma pergunta;
2. não gere a tarefa como confirmada;
3. não presuma que toda funcionalidade exige novo repositório.

A tarefa de repositório deve reunir:

* criação;
* configuração inicial;
* estrutura mínima;
* permissões;
* políticas;
* pipeline inicial, quando aplicável;
* configuração necessária para iniciar o trabalho.

# Testes funcionais no Xray

## Tarefa de criação dos testes

Crie uma tarefa:

`BACKEND_XRAY_TEST_DESIGN`

Título recomendado:

`[BE][XRAY-DESIGN] Criar cenários de teste de <capacidade> no Xray`

A descrição deve contextualizar:

* história;
* objetivo funcional;
* fluxo;
* critérios de aceite;
* regras;
* exceções;
* sistemas envolvidos.

O escopo deve incluir:

* criar ou atualizar itens de teste no Xray;
* vincular os testes à história;
* definir pré-condições;
* definir dados;
* definir passos;
* definir resultados esperados;
* incluir cenários positivos;
* incluir cenários negativos;
* incluir limites e exceções;
* mapear critérios de aceite cobertos;
* identificar cenários que não puderam ser definidos.

A definição de pronto deve exigir:

* testes existentes no Xray;
* vínculo com a história;
* cobertura dos critérios;
* revisão dos cenários;
* ausência de perguntas bloqueantes para execução.

Essa tarefa não implementa testes unitários.

## Tarefa de execução em homologação

Crie uma tarefa:

`BACKEND_XRAY_TEST_EXECUTION_HML`

Título recomendado:

`[BE][XRAY-EXEC-HML] Executar cenários de <capacidade> em homologação`

A descrição deve incluir:

* versão ou build a ser validada;
* ambiente de homologação;
* testes do Xray que serão executados;
* dados de teste;
* pré-condições;
* evidências necessárias;
* tratamento de falhas;
* registro de defeitos;
* condição para reexecução.

A definição de pronto deve exigir:

* execução registrada no Xray;
* ambiente identificado como homologação;
* versão ou build registrada;
* resultado de cada teste;
* evidências anexadas;
* defeitos vinculados quando houver;
* reexecuções registradas;
* resultado final rastreável.

Por padrão, essa tarefa deve ser executada por alguém diferente do autor
principal da implementação.

Uma exceção deve possuir justificativa e aprovação.

# Validação funcional em homologação

Crie uma tarefa:

`BACKEND_HML_FUNCTIONAL_VALIDATION`

Título recomendado:

`[BE][VALIDATION-HML] Validar funcionalmente <capacidade> em homologação`

Essa atividade não é uma repetição mecânica da execução do Xray.

Ela confirma que o conjunto da entrega atende ao resultado funcional.

A descrição deve incluir:

* contexto;
* objetivo da validação;
* versão em homologação;
* critérios de aceite;
* fluxo ponta a ponta;
* integrações relevantes;
* cenários críticos;
* execução do Xray relacionada;
* defeitos conhecidos;
* evidências;
* critério de aprovação;
* critério de reprovação.

A definição de pronto deve exigir:

* validação feita por pessoa independente do desenvolvimento;
* versão validada registrada;
* critérios de aceite revisados;
* execução Xray referenciada;
* resultado aprovado, aprovado com ressalvas ou reprovado;
* evidências registradas;
* ressalvas ou defeitos documentados.

A pessoa responsável pela execução do Xray pode ser a mesma da validação
funcional, desde que não tenha sido a autora principal do código.

# Desenvolvimento backend

Crie entre uma e três tarefas:

`BACKEND_DEVELOPMENT`

Toda tarefa deve representar um incremento funcional.

Uma tarefa deve ser usada quando o trabalho for coeso.

Duas tarefas devem ser usadas quando existirem dois resultados funcionais
ou sistemas separáveis.

Três tarefas somente devem ser usadas quando existirem três unidades reais
de entrega.

Não divida por:

* controller;
* use case;
* port;
* adapter;
* repository;
* DTO;
* migration;
* camada;
* testes unitários.

Toda tarefa backend de desenvolvimento deve incluir:

* implementação ou manutenção;
* regras e comportamentos do escopo;
* tratamento de erros;
* testes unitários;
* testes de integração ou contrato quando aplicáveis;
* execução das validações automatizadas;
* preservação dos testes existentes;
* correção de regressões provocadas pela mudança.

# Documentação no Confluence

Crie uma tarefa:

`BACKEND_CONFLUENCE_DOCUMENTATION`

Título recomendado:

`[BE][DOC-CONFLUENCE] Documentar <fluxo ou integração> no Confluence`

A tarefa deve planejar a criação ou atualização da documentação.

Não produza a documentação durante o Task Planning.

## Público da documentação

A página deve permitir que:

* outra equipe consuma a API ou fluxo;
* um novo desenvolvedor compreenda a solução;
* a equipe mantenedora identifique responsabilidades;
* suporte compreenda respostas e erros;
* responsáveis por integração encontrem os contratos necessários.

## Conteúdo mínimo

Inclua, quando aplicável:

### Contexto

* objetivo;
* problema;
* escopo;
* fora do escopo;
* sistemas;
* equipes responsáveis.

### Funcionamento

* visão geral;
* pré-condições;
* fluxo principal;
* fluxos alternativos;
* regras relevantes;
* integrações;
* dependências;
* limitações.

### Contrato de consumo

* método;
* rota;
* autenticação;
* autorização;
* headers;
* path parameters;
* query parameters;
* corpo de entrada;
* campos obrigatórios;
* campos opcionais;
* exemplos de requisição.

### Respostas

* resposta de sucesso;
* objeto de saída;
* exemplos;
* códigos de resposta;
* tipos de erro;
* estrutura dos erros;
* mensagens;
* condição que produz cada resposta.

### Swagger de homologação

* URL do Swagger de homologação;
* link direto para a operação específica, quando possível;
* quando o link direto não for possível, instrução clara para localizar
  a rota;
* observação sobre autenticação ou acesso necessário.

### Diagramas

* diagrama de sequência;
* participantes;
* chamadas;
* retornos;
* alternativas e erros relevantes;
* arquivo-fonte PlantUML, quando aplicável;
* representação renderizada ou incorporada na página.

### Rastreabilidade

* história do Jira;
* tarefas relacionadas;
* testes do Xray;
* execução em homologação;
* pull request, quando disponível;
* versão ou data da documentação;
* equipe mantenedora.

## Restrições

Não documente:

* tokens;
* senhas;
* segredos;
* chaves privadas;
* dados pessoais reais;
* credenciais de homologação.

Quando já existir documentação, atualize a página existente.

Não crie uma página duplicada apenas porque a história é nova.

# Ordem e dependências

Ordem recomendada:

```text
Criação de repositório, quando necessária
        ↓
Criação dos cenários no Xray
        ↓
Desenvolvimento backend
        ↓
Disponibilização da versão em homologação
        ↓
Execução dos testes no Xray em homologação
        ↓
Validação funcional independente em homologação
        ↓
Conclusão da documentação no Confluence
```

A criação dos cenários pode ocorrer em paralelo com o início do
desenvolvimento, desde que os requisitos estejam estáveis.

A documentação pode ser iniciada após a implementação, mas sua conclusão
deve refletir o comportamento validado em homologação.

# Independência dos executores

Cada tarefa deve possuir:

* `executor_role`;
* `independence_requirement`.

Valores recomendados:

| Categoria          | Papel recomendado                             | Independência               |
| ------------------ | --------------------------------------------- | --------------------------- |
| Repositório        | Backend / Plataforma / DevOps                 | Não aplicável               |
| Xray Design        | QA / Analista / Dev com revisão               | Revisão recomendada         |
| Desenvolvimento    | Desenvolvedor backend                         | Não aplicável               |
| Xray Execution HML | QA / Validador / Outro desenvolvedor          | Preferencialmente diferente |
| Validação HML      | QA / Analista funcional / Outro desenvolvedor | Deve ser diferente          |
| Confluence         | Dev responsável / Documentation Engineer      | Revisão recomendada         |

Quando a pessoa ainda não for conhecida, utilize o papel.

Não invente nomes.

# Descrição das tarefas

Toda tarefa deve possuir:

## Contexto

Explique o problema, o ator, o fluxo e a história.

## Objetivo

Declare o resultado específico.

## Escopo

Liste o que está incluído.

## Comportamento ou atividade esperada

Explique o que deverá ser feito e qual resultado é esperado.

## Restrições e decisões

Inclua somente decisões aprovadas.

## Entregáveis

Liste resultados concretos.

## Evidências e definição de pronto

Explique como comprovar a conclusão.

## Dependências

Liste tarefas, sistemas, ambientes e decisões.

## Executor recomendado

Informe o papel.

## Restrição de independência

Informe se o executor pode ou não ser o autor da implementação.

## Fora do escopo

Registre exclusões relevantes.

## Referências

Inclua histórias, requisitos, critérios, fluxos e fontes.

# Perguntas de planejamento

Utilize:

`TP-QST-###`

Crie perguntas sobre:

* necessidade de novo repositório;
* projeto e organização do Xray;
* cenários que devem ser criados;
* ambiente de homologação;
* versão disponível;
* responsável pela execução;
* responsável pela validação;
* possibilidade de independência;
* espaço ou página do Confluence;
* URL do Swagger;
* público consumidor;
* documentação existente;
* dependências externas.

Prioridades:

* `P0`: impede a decomposição ou execução;
* `P1`: altera tarefa, dependência ou responsável;
* `P2`: melhora clareza ou rastreabilidade;
* `P3`: detalhe não bloqueante.

# Verificação final

Para cada história backend, confirme:

* novo repositório somente quando necessário;
* existe uma tarefa Xray Design;
* existem de uma a três tarefas de desenvolvimento;
* existe uma tarefa Xray Execution HML;
* existe uma tarefa Validation HML;
* existe uma tarefa Confluence;
* execução ocorre em homologação;
* evidências são exigidas;
* validação é independente;
* Swagger de homologação aparece na documentação;
* respostas e erros aparecem na documentação;
* diagrama de sequência aparece na documentação;
* testes automatizados aparecem dentro do desenvolvimento;
* não existem tarefas divididas apenas por camada.

Para cada história frontend, confirme:

* existem de uma a três tarefas de desenvolvimento;
* não foram criadas quebras automáticas adicionais.

# Prontidão

Defina `jira_ready: true` somente quando:

* o plano estiver validado;
* tarefas obrigatórias estiverem presentes;
* tarefas condicionais estiverem justificadas;
* descrições estiverem completas;
* dependências estiverem registradas;
* Xray e homologação estiverem tratados;
* independência da validação estiver tratada;
* documentação no Confluence estiver definida;
* perguntas P0 estiverem resolvidas.

Defina `handoff_ready: true` quando:

* `jira_ready` for verdadeiro;
* tarefas de desenvolvimento estiverem definidas;
* o Technical Designer tiver contexto suficiente;
* pendências restantes forem internas à implementação.

# Atualização incremental

Ao receber ajustes:

1. preserve IDs;
2. altere somente tarefas impactadas;
3. atualize dependências;
4. atualize papéis;
5. atualize restrições de independência;
6. atualize a cobertura;
7. marque tarefas removidas como `Superseded` ou `Cancelled`;
8. incremente a revisão;
9. registre o histórico.
