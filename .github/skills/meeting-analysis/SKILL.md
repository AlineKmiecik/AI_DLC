---
name: meeting-analysis
description: Metodologia para analisar, resumir, revisar e validar transcrições de reuniões, incluindo prints, protótipos, mensagens de erro e outras evidências visuais. Use quando o Meeting Analyst receber uma nova reunião ou ajustes em um resumo existente.
---

# Objetivo

Transformar uma transcrição potencialmente extensa, repetitiva ou imprecisa
em um artefato conciso, verificável e adequado para revisão humana.

Esta skill não cria requisitos formais, histórias do Jira, tarefas técnicas,
arquitetura ou código.

# Artefato obrigatório

Utilize o template:

`meeting-summary-template.md`

Produza ou atualize:

`docs/ai-dlc/meetings/<meeting-id>/meeting-analysis.md`

Mantenha todos os títulos do template, mesmo quando uma seção não possuir
conteúdo.

Para seções vazias, utilize:

`Nenhum item identificado.`

Isso permite que agentes posteriores distingam uma seção analisada e vazia
de uma seção esquecida.

# Classificação das informações

Toda informação relevante deve pertencer a uma das categorias abaixo.

## Decisão confirmada

Use quando uma decisão foi explicitamente aprovada ou reconhecida durante
a reunião.

Exemplos:

- "Vamos utilizar autenticação por e-mail."
- "A equipe aprovou manter o endpoint atual."
- "Ficou decidido que o processamento será assíncrono."

## Necessidade mencionada

Use quando alguém expressou algo que o sistema ou a equipe precisa fazer,
mas ainda não existe formalização suficiente para tratar como requisito.

Exemplos:

- "Precisamos mostrar o motivo da rejeição."
- "Seria importante conseguir filtrar por empresa."

## Regra ou restrição citada

Use para regras de negócio, limitações técnicas ou condições operacionais
explicitamente mencionadas.

Exemplos:

- "Somente usuários administradores podem realizar a operação."
- "O sistema externo aceita no máximo cinquenta itens por lote."

## Ação

Use quando uma pessoa ou equipe ficou responsável por realizar algo.

Registre:

- ação;
- responsável;
- prazo, quando informado;
- situação.

## Dúvida

Use quando a resposta ainda precisa ser fornecida por uma pessoa, equipe
ou fonte autorizada.

## Hipótese

Use quando existe uma interpretação possível, mas insuficientemente
sustentada.

Hipóteses nunca devem aparecer em decisões confirmadas.

## Inconsistência

Use quando:

- a transcrição parece incorreta;
- duas pessoas deram respostas incompatíveis;
- imagem e transcrição não coincidem;
- um termo técnico não pôde ser identificado;
- uma informação mudou ao longo da reunião sem confirmação final.

# Processo de análise

## Passo 1 — Inventariar as fontes

Liste:

- arquivo principal de transcrição;
- arquivos complementares;
- imagens;
- protótipos;
- mensagens de erro;
- correções já fornecidas pelo usuário.

Não comece pela síntese antes de identificar todas as fontes.

## Passo 2 — Limpar o ruído

Desconsidere no resumo:

- cumprimentos;
- conversas paralelas;
- repetições sem informação nova;
- interrupções;
- confirmações sociais como "sim", "certo" e "entendi";
- explicações abandonadas e imediatamente corrigidas;
- falas sem relação com a demanda.

Não desconsidere uma repetição quando ela representar confirmação de uma
decisão ou esclarecimento de uma regra.

## Passo 3 — Preservar informações críticas

Priorize:

- problema de negócio;
- objetivo da mudança;
- sistemas envolvidos;
- decisões;
- restrições;
- valores, limites, datas e prazos;
- nomes de integrações;
- erros apresentados;
- impactos relatados;
- dependências;
- responsáveis;
- dúvidas que impedem avanço.

## Passo 4 — Tratar falhas de transcrição

Quando um termo parecer incorreto:

1. não corrija silenciosamente;
2. registre o trecho como baixa confiança;
3. proponha a interpretação apenas como hipótese;
4. solicite confirmação ao usuário.

Exemplo:

Transcrição:

`A chamada será feita pelo barramento CCAF.`

Saída:

- Termo transcrito: `CCAF`
- Possível interpretação: `Kafka`
- Classificação: baixa confiança
- Ação necessária: confirmar o nome da tecnologia

## Passo 5 — Analisar imagens

Para cada imagem, registre:

- identificador;
- arquivo;
- tipo de evidência;
- observações visuais;
- textos legíveis;
- relação com a reunião;
- hipótese, quando houver;
- pergunta aberta.

Separe sempre:

### Observação

Algo diretamente visível.

Exemplo:

`A imagem exibe a mensagem "Usuário sem permissão".`

### Interpretação

Uma explicação possível.

Exemplo:

`A mensagem pode estar relacionada à validação de perfil.`

A interpretação deve ser registrada como hipótese, salvo quando houver
confirmação em outra fonte.

## Passo 6 — Criar a síntese

O resumo executivo deve:

- possuir no máximo oito itens;
- usar uma frase por item;
- apresentar o problema, objetivo e principais decisões;
- evitar detalhes técnicos ainda não validados;
- não repetir o conteúdo completo das outras seções.

## Passo 7 — Criar rastreabilidade

Sempre que possível, associe informações importantes a:

- timestamp;
- intervalo de timestamps;
- número da linha;
- nome do arquivo;
- identificador da imagem.

Formatos recomendados:

- `TRANSCRIPT 00:14:20–00:15:05`
- `TRANSCRIPT linhas 120–138`
- `IMG-01`
- `Anotação do usuário — revisão 2`

Se a fonte não possuir timestamps nem linhas estáveis, utilize um trecho
curto de referência, sem copiar grandes partes da transcrição.

## Passo 8 — Identificar bloqueios

Para cada dúvida aberta, indique:

- quem pode responder;
- impacto;
- se ela bloqueia a próxima etapa;
- qual informação é necessária.

Não classifique toda dúvida como bloqueante.

## Passo 9 — Revisar antes de salvar

Verifique:

- se alguma hipótese foi apresentada como fato;
- se alguma decisão está sem evidência;
- se uma correção do usuário foi aplicada;
- se existem contradições não registradas;
- se as imagens foram tratadas como evidência separada;
- se o resumo está realmente menor do que a transcrição;
- se foram criadas histórias ou tarefas indevidamente;
- se o status está correto.

# Processo de ajuste

Ao receber ajustes do usuário:

1. leia a revisão atual;
2. aplique as mudanças solicitadas;
3. atualize seções impactadas;
4. incremente `revision`;
5. atualize `updated_at` somente quando a informação estiver disponível;
6. adicione uma linha ao histórico;
7. não reescreva todo o documento sem necessidade;
8. mantenha o status como `draft`, salvo validação explícita.

# Critério de handoff

Defina `handoff_ready: true` somente quando:

- o usuário tiver validado o documento;
- todas as inconsistências relevantes estiverem explícitas;
- dúvidas bloqueantes tiverem sido respondidas ou aceitas conscientemente;
- as fontes utilizadas estiverem registradas.

Um documento pode ser validado contendo dúvidas não bloqueantes.

# Economia de contexto

Não replique a transcrição no artefato.

Não inclua grandes citações.

Não repita a mesma informação em várias seções.

Prefira referências aos trechos originais.

No chat, apresente apenas um resumo das alterações e o caminho do artefato.