---

name: meeting-analysis
description: Metodologia para analisar e resumir reuniões a partir de transcrições em português ou inglês, anotações fornecidas pelo usuário no chat ou uma combinação dessas fontes. Permite operar sem transcrição, consolidar correções de reconhecimento de fala, incorporar imagens e produzir sempre um meeting-analysis.md em português.
-----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------

# Objetivo

Transformar informações relacionadas a uma reunião em um artefato:

* conciso;
* factual;
* rastreável;
* revisável;
* adequado para a próxima etapa do AI-DLC.

Uma transcrição é opcional.

As anotações e o contexto fornecidos pelo usuário no chat são fontes
válidas e podem ser utilizados como entrada principal.

# Artefato obrigatório

Utilize:

`meeting-summary-template.md`

Produza ou atualize:

`docs/ai-dlc/meetings/<meeting-id>/meeting-analysis.md`

Quando o usuário indicar outro caminho, utilize o caminho informado.

Mantenha todas as seções do template.

Quando uma seção tiver sido analisada e estiver vazia, utilize:

`Nenhum item identificado.`

# Idioma de saída

A saída deve ser sempre em português do Brasil.

Isso se aplica a:

* frontmatter;
* títulos;
* descrições;
* tabelas;
* decisões;
* ações;
* perguntas;
* inconsistências;
* histórico;
* resposta no chat.

Fontes podem estar em português ou inglês.

Preserve no idioma original:

* nomes;
* siglas;
* tecnologias;
* campos;
* rotas;
* código;
* mensagens de erro;
* identificadores;
* pequenos trechos necessários para evidência.

# Passo 1 — Determinar o modo de entrada

Classifique como:

## `notes-only`

Não existe transcrição.

Existem anotações, contexto, tópicos ou relato fornecido pelo usuário.

## `transcript-only`

Existe transcrição.

Não existem anotações ou correções adicionais relevantes.

## `transcript-and-notes`

Existem transcrição e anotações, contexto ou correções do usuário.

Registre o modo no frontmatter e na situação da análise.

# Passo 2 — Inventariar as fontes

Crie IDs para todas as fontes.

## Anotações

Utilize:

* `USR-NOTE-001`;
* `USR-NOTE-002`.

## Contexto confirmado

Utilize:

* `USR-CONTEXT-001`.

## Correções explícitas

Utilize:

* `USR-CORR-001`.

## Transcrições

Utilize:

* `TRN-001`;
* `TRN-002`.

## Imagens

Utilize:

* `IMG-01`;
* `IMG-02`.

## Documentos complementares

Utilize:

* `DOC-001`.

Para cada fonte, registre:

* tipo;
* idioma;
* identificação;
* nível de autoridade;
* finalidade;
* observações.

# Passo 3 — Interpretar a certeza das anotações

Analise a linguagem utilizada pelo usuário.

## Informação assertiva

Exemplos:

* “O sistema é responsável pelo reprocessamento.”
* “A autenticação será feita por e-mail.”
* “Nossa equipe não altera o sistema legado.”

Classifique como contexto ou informação confirmada pelo usuário.

## Correção

Exemplos:

* “O correto é Kafka.”
* “A transcrição entendeu CPF, mas foi dito e-mail.”
* “Isso não foi decidido.”

Classifique como correção explícita.

## Incerteza

Palavras indicativas:

* acho;
* talvez;
* possivelmente;
* provavelmente;
* pode ser;
* não tenho certeza;
* parece.

Classifique como hipótese ou dúvida.

Não transforme frases incertas em decisões.

# Passo 4 — Trabalhar sem transcrição

Quando o modo for `notes-only`:

1. utilize as anotações como fonte principal;
2. não exija arquivo;
3. não invente timestamps;
4. não invente falas;
5. não invente participantes;
6. organize o contexto em linguagem clara;
7. preserve o nível de certeza informado;
8. crie dúvidas para lacunas importantes;
9. registre as limitações da análise;
10. produza um draft completo.

A análise sem transcrição pode conter:

* decisões;
* contexto;
* necessidades;
* regras;
* ações;
* dúvidas;
* fora do escopo.

Esses itens devem referenciar as fontes `USR-*`.

# Passo 5 — Limpar uma transcrição

Quando existir transcrição, desconsidere:

* cumprimentos;
* conversas paralelas;
* repetições sem informação nova;
* interrupções sem conclusão;
* confirmações sociais;
* ruído de reconhecimento de fala;
* trechos fora do contexto.

Preserve:

* decisões;
* necessidades;
* regras;
* restrições;
* números;
* datas;
* responsáveis;
* sistemas;
* mensagens de erro;
* dúvidas;
* correções realizadas durante a própria reunião.

# Passo 6 — Analisar transcrições em inglês

Ao analisar inglês:

1. compreenda a intenção no idioma original;
2. sintetize diretamente em português;
3. não traduza palavra por palavra;
4. preserve termos técnicos;
5. preserve mensagens de erro;
6. registre referências no idioma original;
7. mantenha o nível de certeza da fala.

Exemplo:

```text
Original:
“We might need to add a retry mechanism.”

Resumo:
Foi levantada a possibilidade de adicionar um mecanismo de nova tentativa.

Classificação:
Hipótese ou necessidade mencionada, não decisão confirmada.
```

# Passo 7 — Consolidar transcrição e anotações

Quando o modo for `transcript-and-notes`:

1. leia toda a transcrição;
2. leia todas as anotações;
3. crie um mapa de correções;
4. identifique complementos;
5. identifique divergências;
6. aplique correções explícitas;
7. preserve referências originais;
8. registre a fonte correta;
9. crie uma única síntese.

## Exemplo de correção fonética

Transcrição:

```text
A integração vai publicar no Cafica.
```

Anotação:

```text
Onde aparece Cafica, o correto é Kafka.
```

Resultado:

```text
A integração publicará no Kafka.
```

Rastreabilidade:

```text
TRN-001 00:21:40
USR-CORR-001
```

## Exemplo de complemento

Transcrição:

```text
Nós somente enviaremos a solicitação.
```

Anotação:

```text
O sistema externo é legado e pertence à equipe Financeira.
```

Resultado:

* nossa solução é responsável pelo envio;
* o sistema legado pertence à equipe Financeira;
* a implementação do legado está fora da responsabilidade da equipe.

As origens devem continuar distintas.

# Passo 8 — Resolver conflitos

Quando anotações e transcrição divergirem:

## Correção explícita

Adote a correção do usuário.

Registre:

* texto original;
* valor corrigido;
* fonte;
* impacto.

## Divergência sem correção explícita

Não escolha silenciosamente.

Registre:

* informações conflitantes;
* fontes;
* impacto;
* pergunta necessária.

Exemplo:

```text
Transcrição:
A equipe Financeira realizará o reprocessamento.

Anotação:
A equipe de Plataforma realizará o reprocessamento.
```

Sem uma frase como “o correto é Plataforma”, registre conflito.

# Passo 9 — Analisar imagens

Para cada imagem:

* atribua ID;
* registre arquivo;
* registre idioma dos textos;
* descreva observações;
* preserve mensagens originais;
* explique em português;
* relacione com outras fontes;
* identifique hipóteses;
* crie perguntas.

Separe:

## Observação

Algo visível.

## Interpretação

Possível significado.

A interpretação deve permanecer hipótese até confirmação.

# Passo 10 — Classificar informações

Toda informação relevante deve ser uma das categorias.

## Decisão confirmada

Aprovada explicitamente pelo usuário ou durante a reunião.

## Contexto confirmado

Informação necessária para compreender o cenário.

## Necessidade mencionada

Algo que se espera do sistema ou processo, mas ainda não formalizado.

## Regra ou restrição

Condição de negócio, técnica ou operacional citada.

## Ação

Atividade atribuída a uma pessoa ou equipe.

## Dúvida

Informação que precisa ser respondida.

## Hipótese

Interpretação não confirmada.

## Inconsistência

Conflito, erro de transcrição ou informação de baixa confiança.

# Passo 11 — Construir o resumo executivo

O resumo executivo deve:

* ter no máximo oito itens;
* ser escrito em português;
* explicar problema e objetivo;
* incluir decisões principais;
* incluir impactos relevantes;
* mencionar bloqueios importantes;
* não repetir todas as outras seções.

# Passo 12 — Registrar correções da transcrição

Para cada correção relevante, registre:

* ID;
* trecho ou termo original;
* valor corrigido;
* fonte da correção;
* referência da transcrição;
* seções impactadas.

Não registre correções puramente gramaticais sem impacto.

Registre correções que alterem:

* tecnologia;
* nome;
* sistema;
* ator;
* regra;
* valor;
* prazo;
* responsabilidade;
* comportamento esperado.

# Passo 13 — Criar rastreabilidade

Formatos recomendados:

```text
TRN-001 00:14:20–00:15:05
TRN-001 linhas 120–138
USR-NOTE-001
USR-CONTEXT-001
USR-CORR-001
IMG-01
DOC-001 seção 3
```

Quando a fonte existir somente no chat:

```text
USR-NOTE-001 — contexto fornecido pelo usuário na revisão 1
```

Não invente linhas ou timestamps.

# Passo 14 — Registrar limitações

Quando não houver transcrição, registre possíveis limitações:

* ausência de timestamps;
* impossibilidade de atribuir falas;
* ausência do texto integral;
* contexto baseado nas anotações disponíveis;
* participantes não identificados;
* decisões que precisam de confirmação.

A limitação não deve invalidar automaticamente a análise.

# Passo 15 — Aplicar novas anotações

Quando o usuário enviar novas informações:

1. classifique cada informação;
2. registre nova fonte;
3. identifique itens impactados;
4. atualize apenas as seções necessárias;
5. preserve IDs existentes;
6. incremente a revisão;
7. atualize o histórico;
8. mantenha o status como `draft`.

Não obrigue o usuário a reenviar as fontes anteriores.

# Passo 16 — Revisar consistência

Antes de salvar, verifique:

* todas as fontes foram inventariadas;
* modo de entrada está correto;
* idioma de saída é português;
* termos técnicos foram preservados;
* correções foram aplicadas;
* correções possuem rastreabilidade;
* anotações não foram ignoradas;
* hipóteses não foram tratadas como fatos;
* decisões possuem fonte;
* conflitos foram registrados;
* imagens não foram superinterpretadas;
* o resumo não depende apenas do histórico do chat;
* o artefato contém o contexto necessário para uma nova sessão.

# Passo 17 — Calcular handoff

Defina `handoff_ready: true` somente quando:

* o usuário tiver validado o resumo;
* dúvidas bloqueantes estiverem resolvidas ou aceitas;
* conflitos importantes estiverem explícitos;
* fontes estiverem registradas;
* correções relevantes estiverem incorporadas;
* existir contexto suficiente para o Requirements Engineer.

A ausência de transcrição não impede `handoff_ready: true`.

# Economia de contexto

Não copie integralmente:

* transcrições;
* anotações longas;
* documentos;
* conversas.

Utilize sínteses e referências.

Não repita a mesma informação em várias seções.

No chat, apresente somente:

* caminho;
* revisão;
* status;
* modo de entrada;
* correções;
* mudanças;
* dúvidas.
