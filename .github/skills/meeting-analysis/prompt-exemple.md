-- Primeira análise --
Analise a transcrição:

@docs/reunioes/reuniao-integracao-pagamentos.txt

Meeting ID: PAYMENTS-2026-08-16

A reunião é sobre uma nova integração de pagamentos.

Quero que você:
- identifique o problema discutido;
- decisões tomadas;
- necessidades mencionadas;
- regras ou restrições citadas;
- ações definidas;
- dúvidas ainda abertas;
- possíveis erros de transcrição.

Crie o artefato inicial como draft.
_________________________________________________________________
-- Incorporando novas transcrições (sem concatenar os resumos) --
Analise esta nova transcrição como uma reunião independente.

Meeting ID: PAYMENTS-MEETING-02

@docs/reunioes/reuniao-pagamentos-02.txt

Ela trata da continuação da mesma demanda da reunião PAYMENTS-MEETING-01.

Não consolide os dois resumos.
Apenas registre PAYMENTS-MEETING-01 como reunião relacionada.

_________________________________________________________________
-- Sem transcrição --
Use o Meeting Analyst.

Meeting ID:
PAYMENTS-ALIGNMENT-001

Não tenho uma transcrição. Estas são minhas anotações da reunião:

- Precisamos impedir processamento duplicado de pagamentos.
- Hoje a aplicação reenvia a mesma solicitação quando ocorre timeout.
- O sistema bancário pode ter processado a operação mesmo quando não
  recebemos resposta.
- Foi discutida a necessidade de consultar o status antes de reenviar.
- A equipe de Pagamentos ficará responsável pelo fluxo.
- Não ficou definido por quanto tempo devemos tentar consultar o status.
- O sistema bancário é externo e não será alterado por nossa equipe.

Crie o meeting-analysis.md como draft.

Utilize minhas anotações como fonte principal.
Não invente timestamps ou participantes.
Gere perguntas para as informações que ainda faltam.