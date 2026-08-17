
## 3. `~/.copilot/skills/java-spring-implementation/SKILL.md`

```markdown
---
name: java-spring-implementation
description: Metodologia para implementar tarefas Java e Spring a partir de um Technical Design validado, respeitando o perfil, a arquitetura, as versões, os packages, a segurança e o checklist específico do repositório. Use somente quando coding_enabled estiver true.
---

# Pré-condições

Antes de implementar, confirme:

- existe `project-profile.md`;
- perfil está `validated`;
- onboarding está concluído;
- `coding_enabled` está true;
- idioma está confirmado;
- arquitetura está confirmada;
- checklist existe;
- skill local existe;
- Technical Design está validado;
- `coding_ready` está true.

Se uma condição falhar, não implemente.

# Fontes

Leia:

1. `.github/project/project-profile.md`;
2. `.github/project/project-quality-checklist.md`;
3. `.github/skills/project-standards/SKILL.md`;
4. `.github/copilot-instructions.md`;
5. `.github/instructions/java.instructions.md`;
6. Technical Design;
7. código existente relevante;
8. testes semelhantes;
9. projeto de referência, somente quando autorizado.

# Idioma

Aplique `code_language` somente a código novo.

Não traduza:

- contratos públicos;
- campos de API;
- eventos;
- tópicos;
- nomes externos;
- classes já publicadas;
- propriedades;
- bibliotecas.

Em português:

- não use acentos em identificadores;
- use nomes claros;
- evite abreviações;
- mantenha termos técnicos consolidados.

# Java

Utilize exatamente a versão registrada.

Antes de utilizar um recurso de linguagem:

- confirme que existe na versão configurada;
- confirme que o projeto já o aceita;
- respeite style e ferramentas existentes.

Não altere a versão para permitir um recurso.

# Spring Boot

Utilize os padrões da versão existente.

Não:

- atualize starters;
- altere versão do parent;
- adicione dependência redundante;
- substitua configuração corporativa;
- troque biblioteca existente apenas por preferência.

# Arquitetura

## Hexagonal

Respeite o package map.

Mantenha:

- domínio independente;
- aplicação coordenando casos de uso;
- ports definindo contratos;
- adapters traduzindo tecnologias;
- composição fora do domínio;
- dependências apontando para dentro.

Não coloque:

- regra de negócio em controller;
- regra de negócio em client;
- regra de negócio em repository;
- anotação Spring no domínio quando proibida;
- adapter concreto sendo chamado diretamente pelo domínio.

## MVC

Respeite a separação registrada.

Não permita:

- controller acessando repository diretamente, salvo padrão explicitamente aprovado;
- repository dependente da camada web;
- service dependente de controller;
- lógica de negócio em DTO;
- tratamento de exceção duplicado em cada controller.

# Mudança mínima

Implemente somente o Technical Design.

Não faça:

- refatoração paralela;
- renomeação global;
- atualização de tecnologia;
- reorganização arquitetural;
- limpeza sem relação;
- mudança de estilo em arquivos não afetados.

# Dependências

Antes de adicionar dependência:

- confirme necessidade;
- procure alternativa já existente;
- verifique dependency management;
- obtenha aprovação;
- use versão autorizada;
- registre impacto.

Não informe versão arbitrária.

# Segurança

Verifique:

- validação de entrada;
- autenticação;
- autorização;
- segregação por cliente, empresa ou tenant;
- dados sensíveis;
- logs;
- secrets;
- injeção;
- deserialização;
- chamadas externas;
- timeout;
- retry;
- idempotência;
- mensagens de erro;
- exposição de stack trace;
- permissões.

Nunca grave em log:

- senha;
- token;
- segredo;
- chave;
- Authorization header;
- payload sensível completo;
- dados pessoais sem necessidade.

# Testes

Implemente os testes definidos no Technical Design.

Inclua, quando aplicável:

- unitários;
- integração;
- contrato;
- arquitetura;
- regressão;
- serialização;
- persistência;
- erro;
- autorização;
- idempotência;
- concorrência.

Não remova teste para fazer o build passar.

Não enfraqueça assertion existente sem justificativa.

# Arquitetura automatizada

Execute a ferramenta definida:

- ArchUnit;
- Spring Modulith;
- ferramenta existente;
- outra ferramenta registrada.

Não desative a ferramenta.

Não exclua package apenas para evitar violação.

Se a regra estiver incorreta, interrompa e solicite ajuste no perfil ou
Technical Design.

# Baseline protegida

Antes e depois da implementação, compare:

- versões;
- parent;
- BOM;
- wrappers;
- plugins;
- pipeline;
- arquivos protegidos.

Qualquer diferença não autorizada bloqueia a conclusão.

# Processo

1. Ler contexto.
2. Examinar referências.
3. Confirmar arquivos permitidos.
4. Registrar baseline.
5. Implementar menor incremento.
6. Criar testes.
7. Compilar.
8. Executar testes relacionados.
9. Executar testes completos obrigatórios.
10. Executar arquitetura.
11. Executar segurança e análise estática.
12. Revisar diff.
13. Preencher checklist.
14. Relatar resultados.

# Resultado

Informe:

- arquivos;
- comportamento;
- testes;
- comandos;
- resultados;
- checklist;
- arquitetura;
- baseline;
- desvios;
- bloqueios.