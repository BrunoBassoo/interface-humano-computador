# Registro de eventos

Folha de observação e comentários da sessão **P1** — Victor Perrone de Lima Varela — **14/05/2026**, com rastreabilidade para [V01–V08](../13.0%20Avaliação%20Heurística/Violações%20e%20riscos.md) e [B01–B07](../13.0%20Avaliação%20Heurística/Boas%20práticas%20identificadas.md).

---

## Folha de observação (moderador)

**Participante:** P1 · **Data:** 14/05/2026 · **Moderador:** Guilherme Barboza de Albuquerque

| Tarefa | Início* | Fim* | Sucesso? | Erros / ajudas | Citação ou comportamento relevante |
| :-: | :--- | :--- | :--- | :--- | :--- |
| T1 | 00:08:10 | 00:08:34 | ☑ total | 0 | Login imediato; comentou que credenciais na tela de login ajudam no protótipo acadêmico |
| T2 | 00:09:05 | 00:09:43 | ☑ total | 0 | *"O status na fila ajuda, mas eu não sei quanto falta — coloquem isso ou digam que não há estimativa."* |
| T3 | 00:10:15 | 00:11:27 | ☑ total | 1 hesitação | Alternou *checkboxes*; explicou real vs IA corretamente; hesitou nas cores no tema escuro |
| T4 | 00:12:00 | 00:12:52 | ☑ total | 1 comentário | Exportou CSV; *"Gerou rápido, mas `gaze_entropy_mean` não está explicado aqui."* |
| T5 | 00:13:30 | 00:14:35 | ☑ total | 0 | Identificou envio na fila global e total de vídeos em Administração |

*\*Marcações relativas à gravação OBS `sessao-P1-victor-varela-20260514.mp4`.*

---

## Eventos e comentários observados (consolidado)

| Tarefa | Participante | Evento / comentário (transcrição resumida) | Violação / boa prática |
| :-: | :--- | :--- | :--- |
| **T1** | P1 | *"A separação motorista e admin no login está clara — evita confusão de permissão."* | **B01** — confirma boa prática |
| **T1** | P1 | Durante exploração livre, leu **Sobre** antes de T2: *"Bom que o texto fala em ambiente controlado e estimativa."* | **B04** — confirma |
| **T2** | P1 | Após confirmar envio: *"Na fila está ok, mas sem ETA parece que travou se o processamento demorar."* | **V01** — confirma |
| **T2** | P1 | Feedback imediato ao selecionar arquivo antes de enviar foi elogiado | **B02** — confirma |
| **T3** | P1 | *"Sei qual camada é qual pela legenda, mas no fundo escuro as linhas ficam muito parecidas — fixem cor ou tracejado."* | **V03** — confirma |
| **T3** | P1 | *"O conceito de comparar real e IA numa tela só faz sentido para o TCC — está no lugar certo."* | **B03** — confirma |
| **T3** | P1 | Perguntou o que significa um card de métrica de *gaze* sem passar o mouse | **V08** — confirma |
| **T4** | P1 | *"PDF e CSV visíveis na mesma aba é bom; o CSV precisa de dicionário na hora."* | **V04** — confirma · **B06** parcial |
| **T5** | P1 | *"Para gestão de frota, a fila global resolve; métricas agregadas poderiam ter glossário."* | **V05** — confirma parcial |
| **T5** | P1 | Não acionou fluxos de erro de upload (arquivo válido na demo) | **V07** — não testado |

---

## Hipóteses da heurística — resultado nesta sessão

| ID | Resultado na sessão P1 | Tarefa |
| :-: | :--- | :--- |
| **V01** | ✅ Confirmado (comentário sobre fila sem ETA) | T2 |
| **V02** | ➖ Não acionado (textos longos não impediram tarefas) | T1–T2 |
| **V03** | ✅ Confirmado (contraste real vs IA) | T3 |
| **V04** | ✅ Confirmado (colunas CSV) | T4 |
| **V05** | ✅ Parcial (termos em Administração) | T5 |
| **V06** | ➖ Não testado (sem ação destrutiva no roteiro) | — |
| **V07** | ➖ Não testado (sem falha de upload) | T2 |
| **V08** | ✅ Confirmado (*tooltip* em métricas) | T3 |
| **B03** | ✅ Elogio | T3 |
| **B04** | ✅ Elogio | T1 |
| **B06** | ✅ Localizou exportação; ressalva sobre CSV | T4 |

---

## Teste exploratório prévio (entrega 6 — referência)

Sessão com **Mariana** ([`Teste com participante`](../6.0%20Prototipação/Teste%20com%20participante.md)): pediu definição de “atenção visual”, *tooltips* e confirmação pós-envio — achados **convergentes** com V01, V08 e B02 observados em P1.

---

*Referências: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010. | NIELSEN, J. **Enhancing the explanatory power of usability heuristics**. Proc. CHI, 1994.*
