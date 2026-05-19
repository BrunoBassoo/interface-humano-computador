# Tarefas e métricas

Tarefas scriptadas, critérios de sucesso e consolidação quantitativa do teste com usuários do **BVRAI**, conforme [DECIDE](../12.0%20Planejamento%20da%20Avaliação%20DECIDE/Planejamento%20da%20avaliação%20DECIDE.md) e [metas de usabilidade](../8.0%20Engenharia%20de%20Usabilidade/Metas%20de%20usabilidade.md).

---

## Roteiro entregue ao participante

> *"Você acaba de receber acesso ao sistema **BVRAI** — uma ferramenta web para envio de vídeos de direção, análise comparativa entre o seu padrão de atenção visual (**real**) e uma **estimativa por IA**, e exportação de relatórios. As credenciais de **motorista** são: usuário `usuario` / senha `123456`. Realize as atividades na ordem apresentada. Se tiver dúvidas sobre **o que fazer**, pode perguntar — mas não sobre **como usar o sistema** (onde clicar)."*

| Tarefa | Enunciado entregue ao participante | Critério de sucesso (moderador) |
| :-: | :--- | :--- |
| **T1** | Acesse o sistema com suas credenciais de **motorista** e localize a área onde você enviaria um vídeo | Login sem assistência; aba **Vídeos** visível em ≤ 1 min |
| **T2** | Selecione o modo **predição**, anexe um arquivo de vídeo (ou use o fluxo de demonstração disponível) e **confirme o envio** | Estado na lista visível (na fila / processando / concluído) sem erro de formato |
| **T3** | Abra **Minha análise**, altere sessão ou período se possível, e ative ou desative camadas; **explique em voz alta** a diferença entre olhar real e IA | Usuário articula que um é medição/registro e outro é **estimativa** do modelo |
| **T4** | Gere um **PDF** ou **CSV** em **Relatórios** para um intervalo de datas válido | *Download* iniciado ou ação concluída conforme implementação |
| **T5** | Acesse como **admin** (`admin` / `admin123`), percorra a **fila global** em **Vídeos** e um indicador em **Administração** | Identifica pelo menos um estado de envio e um indicador agregado |

---

## Legenda — grau de sucesso

| Grau | Definição |
| :--- | :--- |
| **Sucesso total** | Tarefa concluída sem ajuda sobre o uso da interface |
| **Sucesso parcial** | Concluída com **uma** dica sobre navegação |
| **Insucesso** | Não concluída no tempo da sessão |

---

## Resultados por tarefa — Participante P1 (Victor Perrone de Lima Varela)

**Data:** 14/05/2026 · **Moderador:** Guilherme Barboza de Albuquerque

| Tarefa | Descrição | Grau de sucesso | Nº erros | Tipos de erros / ajudas | Tempo | Satisfação percebida |
| :-: | :--- | :-: | :-: | :--- | :-: | :-: |
| **T1** | Login como motorista e localizar **Vídeos** | Sucesso total | 0 | — | 24s | Alto |
| **T2** | Predição, anexo e confirmação de envio | Sucesso total | 0 | Comentário sobre fila sem ETA (não impediu a tarefa) | 38s | Alto |
| **T3** | **Minha análise** — camadas real × IA | Sucesso total | 1 | Hesitação ao distinguir cores das camadas no *theme* escuro (V03) | 1min 12s | Médio |
| **T4** | Exportar **CSV** em **Relatórios** | Sucesso total | 1 | Após exportar, perguntou o significado de duas colunas (V04) | 52s | Médio |
| **T5** | Perfil **admin** — fila e **Administração** | Sucesso total | 0 | — | 1min 05s | Alto |
| | **TOTAL** | **5/5 ✓** | **2** | | **4min 31s** | **4,6/5,0** (Likert) |

> **Legenda — Grau de sucesso:** Sucesso total = tarefa concluída sem ajuda · Sucesso parcial = concluída com 1 dica · Insucesso = não concluída  
> **Evidências:** gravação OBS `sessao-P1-victor-varela-20260514.mp4` e questionário bruto no repositório restrito da equipe BVRAI.

### Tempos parciais

| Bloco | Tarefas | Tempo | Meta (entrega 8) |
| :--- | :--- | :--- | :--- |
| Fluxo principal (motorista) | T1 + T2 + T3 | **2min 14s** | ≤ 4 min |
| Sessão completa (T1–T5) | Todas | **4min 31s** | — |

---

## Consolidação da rodada (*n* = 1)

| Tarefa | Taxa de sucesso total | Média de erros | Tempo médio | Observações |
| :-: | :--- | :--- | :--- | :--- |
| **T1** | 100 % | 0 | 24s | Login direto; elogiou separação motorista/admin (B01) |
| **T2** | 100 % | 0 | 38s | Estados “Na fila” / “Concluído” compreendidos (B07); falta de ETA comentada (V01) |
| **T3** | 100 % | 1 | 1min 12s | Explicou corretamente estimativa da IA; contraste real/IA frágil (V03) |
| **T4** | 100 % | 1 | 52s | CSV gerado; colunas sem glossário na mesma tela (V04) |
| **T5** | 100 % | 0 | 1min 05s | Localizou fila global e card agregado em Administração |
| **TOTAL** | **100 % (5/5)** | **2** | **4min 31s** | Participante especialista (orientador) |

---

## Métricas derivadas

| Métrica | Resultado P1 | Meta (entrega 8) | Atingiu? |
| :--- | :--- | :--- | :---: |
| Taxa de conclusão sem ajuda | **100 %** (5/5 tarefas) | ≥ 80 % | ✅ |
| Tempo fluxo principal (T1+T2+T3) | **2min 14s** | ≤ 4 min | ✅ |
| Satisfação geral (Likert) | **4,6 / 5,0** | ≥ 3,8 | ✅ |
| Compreensão “IA ≠ laudo” (afirmação 4) | **5,0 / 5,0** | ≥ 4,0 (média) | ✅ |
| Primeiro upload sem erro de formato (T2) | **Sim** | ≥ 85 % | ✅ |

---

## Comparação com as metas da entrega 8

| Meta de usabilidade | Valor mínimo | Resultado obtido | Atingiu? |
| :--- | :-: | :-: | :-: |
| Taxa de conclusão de tarefas sem ajuda | ≥ 80 % | 100 % (5/5) | ✅ |
| Tempo médio fluxo principal (T1+T2+T3) | ≤ 4 min | 2min 14s | ✅ |
| Satisfação geral (Likert 1–5) | ≥ 3,8 | 4,6 / 5,0 | ✅ |
| Confiança / compreensão sobre papel da IA (afirmação 4) | ≥ 4,0 (média) | 5,0 / 5,0 | ✅ |

---

*Referências: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010. | NIELSEN, J. **Usability Engineering**. Academic Press, 1993.*
