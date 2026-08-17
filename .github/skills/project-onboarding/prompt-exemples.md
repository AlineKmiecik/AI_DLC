________________________________________________________________________________________________________________________________________
______________________________________________________ DADOS DO AGENTE _________________________________________________________________
________________________________________________________________________________________________________________________________________
Depois, durante o onboarding de cada repositório, o agente gera automaticamente os arquivos específicos daquele projeto, como:
.github/project/project-profile.md
.github/project/project-quality-checklist.md
.github/project/project-onboarding-report.md
.github/project/reference-project-analysis.md
.github/skills/project-standards/SKILL.md
.github/copilot-instructions.md
.github/instructions/java.instructions.md


________________________________________________________________________________________________________________________________________
_______________________________________________ repositório novo com template __________________________________________________________
________________________________________________________________________________________________________________________________________
Use o Coding Agent.

Este é o primeiro uso neste repositório.

Faça o onboarding do projeto antes de qualquer geração ou alteração de código.

Analise o repositório atual e identifique:
- se existe template;
- versão do Java;
- versão do Spring Boot;
- Maven ou Gradle;
- plugins;
- dependências;
- Maven Wrapper ou Gradle Wrapper;
- configurações de pipeline e esteira;
- package base atual;
- estrutura de diretórios;
- exemplos existentes no template;
- arquitetura candidata;
- comandos de build e testes;
- ferramentas de qualidade e segurança existentes.

Não altere nenhum arquivo ainda.

Gere o diagnóstico e faça somente as perguntas necessárias para completar
o perfil do projeto.

Considere versões, pipeline, parent, BOM, wrappers e configurações
corporativas como protegidos.


________________________________________________________________________________________________________________________________________
_______________________________________________ Respondendo às perguntas do onboarding _________________________________________________
________________________________________________________________________________________________________________________________________
Continue o onboarding com estas definições:

- Tipo do projeto: SRV
- Idioma do código: português do Brasil
- Arquitetura: hexagonal
- Package base: br.com.bradesco.pagamentos
- Utilize a versão do Java encontrada no template.
- Utilize a versão do Spring Boot encontrada no template.
- Utilize o Maven configurado pelo template.
- Não altere versões.
- Não altere pipeline.
- Não altere parent ou BOM.
- Não altere versões de plugins.
- Os exemplos do template podem ser removidos.
- Quero utilizar ArchUnit para validar a arquitetura.

Atualize o perfil e o relatório de onboarding.

Ainda não aplique alterações no código.

Apresente primeiro o plano de configuração inicial para minha aprovação.

________________________________________________________________________________________________________________________________________
________________________________________________ Usando outro projeto como referência __________________________________________________
________________________________________________________________________________________________________________________________________

Continue o onboarding deste projeto.

Quero utilizar o projeto abaixo como referência:

../srv-pagamentos-referencia

Trate esse projeto exclusivamente como leitura.

Compare com o projeto atual e identifique padrões relevantes de:
- arquitetura;
- organização de packages;
- controllers;
- use cases;
- ports;
- adapters;
- tratamento de erros;
- logging;
- validações;
- testes;
- segurança;
- Swagger;
- observabilidade.

Não copie:
- versões;
- pipeline;
- package base;
- artifactId;
- configurações de ambiente;
- URLs;
- credenciais;
- secrets.

Registre quais padrões você recomenda:
- adotar;
- adaptar;
- ignorar;
- confirmar comigo.

Não altere o projeto atual ainda.

________________________________________________________________________________________________________________________________________
_________________________________________________ Aplicando a configuração inicial _____________________________________________________
________________________________________________________________________________________________________________________________________

Aprovo o plano de onboarding.

Pode aplicar a configuração inicial conforme o plano aprovado.

Pode:
- remover os exemplos de template que foram aprovados;
- corrigir o package base;
- renomear os diretórios Java correspondentes;
- atualizar os imports afetados;
- atualizar os packages dos testes;
- manter os plugins classificados como KEEP;
- preservar os plugins classificados como PROTECTED;
- configurar a validação arquitetural aprovada;
- gerar as instruções e a skill específica deste projeto.

Não altere:
- versão do Java;
- versão do Spring Boot;
- parent;
- BOM;
- Maven Wrapper;
- versões de plugins;
- pipeline;
- configurações corporativas da esteira.

Ao terminar:
- execute os comandos de validação identificados;
- valide a arquitetura;
- compare a baseline protegida;
- atualize o perfil;
- só habilite coding_enabled se todas as validações obrigatórias passarem.

________________________________________________________________________________________________________________________________________
_________________________________________________ Projeto completamente vazio __________________________________________________________
________________________________________________________________________________________________________________________________________

Use o Coding Agent.

Este é o primeiro uso neste repositório e ele está vazio.

O projeto deverá ser criado do zero.

Não gere nenhum código ainda.

Inicie o onboarding e faça todas as perguntas necessárias para definir:
- versão do Java;
- uso ou não de Spring Boot;
- versão do Spring Boot;
- Maven ou Gradle;
- groupId;
- artifactId;
- nome;
- descrição;
- package base;
- JAR ou WAR;
- arquitetura;
- idioma do código;
- tipo do projeto;
- dependências iniciais;
- ferramenta de validação arquitetural;
- método aprovado para geração do projeto;
- projeto de referência, se houver.

Não escolha versões automaticamente.

Depois das minhas respostas, gere o perfil e o plano de criação em draft
e aguarde minha aprovação antes de criar o projeto.

________________________________________________________________________________________________________________________________________
_________________________________________________ Projeto existente que nunca passou pelo onboarding ___________________________________
________________________________________________________________________________________________________________________________________
Use o Coding Agent.

Este projeto já possui código e está em funcionamento, mas ainda não possui
o Project Profile do Coding Agent.

Não altere código.

Faça o onboarding do projeto existente.

Descubra os padrões atualmente utilizados e gere:
- diagnóstico;
- perfil;
- checklist;
- skill específica do projeto;
- instruções Java.

Quando uma informação puder ser identificada com segurança no projeto,
registre-a como detectada.

Quando depender de decisão da equipe, pergunte.

Não tente reorganizar o projeto para se adequar a uma arquitetura diferente
da existente.

________________________________________________________________________________________________________________________________________
_________________________________________________ Projeto existente que nunca passou pelo onboarding ___________________________________
________________________________________________________________________________________________________________________________________
Use o Coding Agent.

Implemente a TASK-002.

Technical Design:

@docs/ai-dlc/work-items/PAYMENTS-001/technical-design/TASK-002-technical-design.md

Utilize obrigatoriamente:
- o Project Profile;
- o Project Quality Checklist;
- a skill project-standards;
- as instruções Java deste repositório;
- o contrato para o Coding Agent definido no Technical Design.

Implemente somente o escopo da TASK-002.

Execute os testes e validações definidos para o projeto.

Não altere nenhum item da baseline protegida.

Interrompa e me pergunte caso seja necessário sair do Technical Design.

________________________________________________________________________________________________________________________________________
______________________________________ Implementação com uma orientação adicional ______________________________________________________
________________________________________________________________________________________________________________________________________
Use o Coding Agent para implementar a TASK-004.

Technical Design:

@docs/ai-dlc/work-items/AUTH-001/technical-design/TASK-004-technical-design.md

Contexto adicional:

O comportamento existente de autenticação não pode ser alterado.
A nova funcionalidade deve ser aditiva.

Não faça refatorações nos fluxos existentes que não sejam necessárias
para esta tarefa.

Utilize o perfil e os padrões deste projeto.

Execute todas as validações obrigatórias antes de concluir.

________________________________________________________________________________________________________________________________________
______________________________________ Continuar uma implementação interrompida ________________________________________________________
________________________________________________________________________________________________________________________________________
Continue a implementação da TASK-002.

Antes de continuar:
- releia o Technical Design;
- releia o Project Profile;
- releia o checklist;
- verifique o diff atual;
- identifique o que já foi implementado;
- identifique o que ainda falta.

Não refaça código já concluído sem necessidade.

Continue somente dentro do escopo original.

Ao finalizar, execute novamente as validações obrigatórias.

________________________________________________________________________________________________________________________________________
______________________________________ Pedir apenas análise antes de codificar _________________________________________________________
________________________________________________________________________________________________________________________________________
Analise a implementação da TASK-006 antes de alterar qualquer arquivo.

Leia:
- Technical Design;
- Project Profile;
- Project Quality Checklist;
- padrões locais;
- código relacionado.

Depois me apresente:
- arquivos que pretende alterar;
- arquivos que pretende criar;
- testes que pretende criar ou modificar;
- comandos que pretende executar;
- riscos encontrados;
- qualquer divergência entre Technical Design e código atual.

Não altere nenhum arquivo ainda.

________________________________________________________________________________________________________________________________________
______________________________________ Manutenção/correção em código existente _________________________________________________________
________________________________________________________________________________________________________________________________________
Use o Coding Agent.

Implemente a correção definida na TASK-009.

Technical Design:

@docs/ai-dlc/work-items/PAYMENTS-002/technical-design/TASK-009-technical-design.md

Antes de alterar:
- identifique o comportamento atual;
- localize os testes existentes;
- confirme a causa descrita no Technical Design.

Faça a menor alteração possível.

Não aproveite a correção para realizar refatorações não relacionadas.

Adicione ou atualize testes que comprovem:
- o comportamento incorreto anterior;
- o comportamento esperado após a correção;
- a ausência de regressão nos cenários relacionados.

Execute o checklist completo antes de concluir.

________________________________________________________________________________________________________________________________________
____________________________ Quando você suspeita que será necessária uma nova dependência _____________________________________________
________________________________________________________________________________________________________________________________________

Analise a TASK-011.

Technical Design:

@docs/ai-dlc/work-items/PAYMENTS-003/technical-design/TASK-011-technical-design.md

Suspeito que a implementação possa exigir uma nova dependência.

Antes de adicionar qualquer dependência:

1. verifique se o projeto já possui recurso equivalente;
2. verifique se alguma dependência existente resolve a necessidade;
3. verifique o dependency management;
4. identifique exatamente qual dependência seria necessária;
5. explique por que ela é necessária;
6. informe de onde viria sua versão.

Não altere o pom.xml ainda.

Aguarde minha aprovação caso realmente seja necessária uma nova dependência.

________________________________________________________________________________________________________________________________________
___________________________________________ Só executar as validações __________________________________________________________________
________________________________________________________________________________________________________________________________________

Use os padrões do Coding Agent para validar a implementação atual.

Não altere código inicialmente.

Leia:
- Project Profile;
- Project Quality Checklist;
- project-standards.

Depois:
- execute os comandos obrigatórios;
- execute os testes;
- execute a validação arquitetural;
- verifique a baseline protegida;
- revise o diff contra o checklist.

Me apresente as violações encontradas.

Não corrija nada até eu autorizar.