--------- 1- Inicializar o índice ---------
Use o Technical Designer.

Work item:
PAYMENTS-2026-001

Baselines:
@docs/ai-dlc/work-items/PAYMENTS-2026-001/requirements-analysis.md
@docs/ai-dlc/work-items/PAYMENTS-2026-001/business-solution-model.md
@docs/ai-dlc/work-items/PAYMENTS-2026-001/task-plan.md

Crie somente o índice:

docs/ai-dlc/work-items/PAYMENTS-2026-001/technical-design/technical-design-index.md

Identifique:

- tarefas de desenvolvimento backend;
- tarefas de setup de repositório;
- dependências entre desenhos;
- ordem recomendada.

Não produza ainda os desenhos individuais.
Não altere código.

--------- 2. Desenhar uma tarefa por vez ---------
Use o Technical Designer.

Work item:
PAYMENTS-2026-001

Tarefa:
TASK-002

Task plan:
@docs/ai-dlc/work-items/PAYMENTS-2026-001/task-plan.md

Requirements:
@docs/ai-dlc/work-items/PAYMENTS-2026-001/requirements-analysis.md

Solution model:
@docs/ai-dlc/work-items/PAYMENTS-2026-001/business-solution-model.md

Repositório:
o projeto atualmente aberto no IntelliJ.

Quero que você:

1. leia as instruções do repositório;
2. localize fluxos semelhantes;
3. identifique os módulos e arquivos impactados;
4. descreva a solução respeitando a arquitetura hexagonal existente;
5. defina ports e adapters somente quando sustentados pelo projeto;
6. defina contratos, erros, configurações e testes;
7. gere os diagramas PlantUML aplicáveis;
8. crie o contrato para o Coding Agent;
9. registre perguntas e riscos.

Crie:

docs/ai-dlc/work-items/PAYMENTS-2026-001/technical-design/TASK-002-technical-design.md

Não altere nenhum arquivo de código.
Mantenha o desenho como draft.

--------- 3. Solicitar ajuste localizado ---------

Revise o desenho da TASK-002.

Ajustes:

1. O projeto já possui o port PaymentStatusGateway.
   Não proponha um novo port.

2. O adapter que deve ser alterado é:
   infrastructure/payment/PaymentStatusHttpAdapter.java

3. A regra de classificação deve permanecer no domínio,
   e não no adapter HTTP.

4. O timeout ainda não foi definido.
   Remova o valor proposto e crie uma pergunta técnica.

Atualize:

- evidências do repositório;
- mapeamento hexagonal;
- impacto em arquivos;
- integração;
- perguntas;
- diagrama de componentes;
- sequência principal;
- contrato do Coding Agent.

Não altere outras seções.
Incremente a revisão e mantenha como draft.