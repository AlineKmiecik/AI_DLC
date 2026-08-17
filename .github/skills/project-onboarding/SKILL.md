---
name: project-onboarding
description: Diagnostica e configura pela primeira vez um repositório Java. Use quando o perfil do projeto não existir, estiver incompleto ou quando o projeto vier de template, estiver vazio ou precisar ser comparado a outro projeto. Gera o perfil, checklist, instruções e skill específica do repositório antes de permitir geração de código.
---

# Objetivo

Transformar um repositório desconhecido em um projeto com contexto
persistente e validado para utilização pelo Coding Agent.

O onboarding deve produzir:

- diagnóstico;
- decisões;
- perfil;
- checklist;
- instruções;
- skill local;
- baseline protegida;
- comandos validados;
- estratégia de arquitetura;
- autorização explícita para geração de código.

# Regra principal

Na primeira execução, não implemente funcionalidade de negócio.

Primeiro diagnostique.

Depois pergunte.

Depois registre.

Depois solicite aprovação.

Somente após aprovação aplique a configuração inicial.

# Arquivos de saída

Crie ou atualize:

```text
.github/project/project-profile.md
.github/project/project-quality-checklist.md
.github/project/project-onboarding-report.md
.github/project/reference-project-analysis.md
.github/skills/project-standards/SKILL.md
.github/copilot-instructions.md
.github/instructions/java.instructions.md