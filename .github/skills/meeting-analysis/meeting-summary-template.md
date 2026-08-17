---

artifact_type: meeting-analysis
schema_version: "2.0"
meeting_id: "<meeting-id>"
title: "<título da reunião ou alinhamento>"
meeting_date: "<YYYY-MM-DD ou não informado>"
status: "draft"
revision: 1
handoff_ready: false
source_mode: "<notes-only | transcript-only | transcript-and-notes>"
source_languages: []
output_language: "pt-BR"
source_inputs: []
transcript_files: []
image_files: []
created_by: "Meeting Analyst"
created_at: "<data/hora ou não informado>"
updated_at: "<data/hora ou não informado>"
validated_by: null
validated_at: null
------------------

# Análise da reunião — <título>

## 1. Situação da análise

* Meeting ID: `<meeting-id>`
* Status: `<draft ou validated>`
* Revisão: `<número>`
* Modo de entrada: `<notes-only | transcript-only | transcript-and-notes>`
* Idiomas das fontes: `<português, inglês ou ambos>`
* Idioma do resumo: `Português do Brasil`
* Transcrição disponível: `<sim ou não>`
* Anotações do usuário disponíveis: `<sim ou não>`
* Imagens ou documentos complementares: `<quantidade>`
* Pronto para handoff: `<sim ou não>`

## 2. Resumo executivo

* <Problema ou assunto principal>
* <Objetivo da discussão>
* <Decisão ou conclusão relevante>
* <Impacto relevante>
* <Principal dúvida ou bloqueio>

Máximo de oito itens.

## 3. Fontes e cobertura

| ID           | Fonte                             | Tipo        | Idioma                             | Autoridade   | Utilização              |
| ------------ | --------------------------------- | ----------- | ---------------------------------- | ------------ | ----------------------- |
| USR-NOTE-001 | Anotações fornecidas pelo usuário | Anotação    | Português                          | Média / Alta | Contexto principal      |
| USR-CORR-001 | Correção fornecida pelo usuário   | Correção    | Português                          | Alta         | Correção da transcrição |
| TRN-001      | <arquivo>                         | Transcrição | Português / Inglês                 | Média / Alta | Registro da reunião     |
| IMG-01       | <arquivo>                         | Imagem      | Português / Inglês / Não aplicável | Complementar | Evidência visual        |

## 4. Limitações da análise

* <ausência de transcrição, timestamps, identificação de participantes ou outra limitação>
* <informação que não pôde ser confirmada>
* <parte do contexto baseada somente em anotações>

Quando não houver limitações relevantes:

`Nenhuma limitação relevante identificada.`

## 5. Contexto e problema

### Contexto

<Descrição consolidada do cenário.>

### Problema

<Descrição objetiva do problema ou assunto discutido.>

### Resultado esperado mencionado

<Resultado esperado conforme as fontes, sem formalizar requisitos.>

## 6. Correções aplicadas à transcrição

| ID      | Registro original                | Correção adotada | Origem da correção | Referência original          | Impacto             |
| ------- | -------------------------------- | ---------------- | ------------------ | ---------------------------- | ------------------- |
| COR-001 | <termo ou informação transcrita> | <valor correto>  | <USR-CORR-###>     | <TRN-### timestamp ou linha> | <seções impactadas> |

Quando não houver transcrição:

`Não aplicável — análise realizada sem transcrição.`

Quando houver transcrição sem correções:

`Nenhuma correção relevante aplicada.`

## 7. Decisões confirmadas

| ID     | Decisão   | Evidência         | Confiança    |
| ------ | --------- | ----------------- | ------------ |
| DEC-01 | <decisão> | <USR/TRN/DOC/IMG> | Alta / Média |

Use `Nenhum item identificado.` quando não houver decisão confirmada.

## 8. Contextos confirmados pelo usuário

| ID     | Contexto             | Origem            | Impacto no entendimento |
| ------ | -------------------- | ----------------- | ----------------------- |
| CTX-01 | <contexto adicional> | <USR-CONTEXT-###> | <impacto>               |

Esta seção é especialmente importante quando o contexto não foi verbalizado
na reunião ou quando não existe transcrição.

## 9. Necessidades mencionadas

| ID     | Necessidade   | Origem  | Situação                             |
| ------ | ------------- | ------- | ------------------------------------ |
| NEC-01 | <necessidade> | <fonte> | Mencionada / Confirmada pelo usuário |

Estas necessidades ainda não são histórias nem requisitos formais.

## 10. Regras e restrições citadas

| ID     | Regra ou restrição   | Evidência | Confiança            |
| ------ | -------------------- | --------- | -------------------- |
| REG-01 | <regra ou restrição> | <fonte>   | Alta / Média / Baixa |

## 11. Sistemas, áreas e pessoas envolvidas

### Sistemas

* <sistema>

### Áreas ou equipes

* <área ou equipe>

### Participantes relevantes

* <nome ou papel>

Não invente participantes quando a fonte não os identificar.

## 12. Ações identificadas

| ID     | Ação   | Responsável                       | Prazo                    | Situação | Evidência |
| ------ | ------ | --------------------------------- | ------------------------ | -------- | --------- |
| ACT-01 | <ação> | <pessoa, equipe ou não informado> | <prazo ou não informado> | Aberta   | <fonte>   |

## 13. Evidências visuais

| ID     | Arquivo   | Texto original relevante       | Observação objetiva | Relação com o contexto | Hipótese ou dúvida     |
| ------ | --------- | ------------------------------ | ------------------- | ---------------------- | ---------------------- |
| IMG-01 | <arquivo> | <texto em português ou inglês> | <observação>        | <relação>              | <hipótese ou pergunta> |

## 14. Dúvidas abertas

| ID     | Dúvida                | Quem pode responder | Impacto   | Bloqueante | Origem  |
| ------ | --------------------- | ------------------- | --------- | ---------- | ------- |
| QST-01 | <pergunta específica> | <pessoa ou equipe>  | <impacto> | Sim / Não  | <fonte> |

## 15. Hipóteses

| ID     | Hipótese   | Origem  | Motivo da incerteza | Pergunta relacionada |
| ------ | ---------- | ------- | ------------------- | -------------------- |
| HYP-01 | <hipótese> | <fonte> | <motivo>            | <QST-###>            |

Hipóteses não são decisões confirmadas.

## 16. Inconsistências e informações de baixa confiança

| ID     | Informação   | Fontes envolvidas | Motivo   | Possível interpretação | Ação necessária          |
| ------ | ------------ | ----------------- | -------- | ---------------------- | ------------------------ |
| UNC-01 | <informação> | <TRN/USR/DOC/IMG> | <motivo> | <hipótese>             | <confirmação necessária> |

## 17. Itens explicitamente fora do escopo

* <item declarado fora do escopo>

Não inferir itens fora do escopo sem uma fonte.

## 18. Índice das fontes

| ID           | Tipo                | Identificação                   | Idioma        | Observação        |
| ------------ | ------------------- | ------------------------------- | ------------- | ----------------- |
| USR-NOTE-001 | Anotação do usuário | Contexto fornecido na revisão 1 | Português     | <descrição curta> |
| USR-CORR-001 | Correção do usuário | Correção fornecida na revisão 2 | Português     | <descrição curta> |
| TRN-001      | Transcrição         | <caminho>                       | Inglês        | <descrição curta> |
| IMG-01       | Imagem              | <arquivo>                       | Não aplicável | <descrição curta> |

## 19. Condição para próxima etapa

* Resumo revisado pelo usuário: `<sim ou não>`
* Fontes registradas: `<sim ou não>`
* Correções relevantes incorporadas: `<sim, não ou não aplicável>`
* Existem dúvidas bloqueantes: `<sim ou não>`
* Existem conflitos relevantes abertos: `<sim ou não>`
* Contexto suficiente para Requirements Engineer: `<sim ou não>`
* Artefato validado pelo usuário: `<sim ou não>`
* Pronto para handoff: `<sim ou não>`

### Bloqueios para handoff

* <QST-###, UNC-### ou nenhum bloqueio>

## 20. Histórico de revisões

| Revisão | Data                    | Autor           | Alteração                                      |
| ------- | ----------------------- | --------------- | ---------------------------------------------- |
| 1       | <data ou não informada> | Meeting Analyst | Criação inicial a partir das fontes informadas |
