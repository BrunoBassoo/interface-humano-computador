# Conclusão e reprojeto

Síntese dos resultados do teste com usuários do **BVRAI** — rodada com **1** participante (P1, orientador Prof. Dr. Victor Perrone de Lima Varela) — e plano de reprojeto encadeado à [síntese heurística](../13.0%20Avaliação%20Heurística/Síntese%20e%20priorização%20de%20correções.md).

---

## Síntese dos resultados

### Desempenho geral

- **Participantes:** *n* = **1** (código **P1** — Victor Perrone de Lima Varela, orientador do TCC)  
- **Taxa de conclusão sem ajuda:** **100 %** (5/5 tarefas)  
- **Tempo médio T1+T2+T3:** **2min 14s**  
- **Satisfação média (Likert):** **4,6 / 5,0**  
- **Compreensão IA como estimativa (afirmação 4):** **5,0 / 5,0**  

O teste confirmou que o fluxo principal do BVRAI no protótipo `bvrai-interface` é **operável** com conclusão integral das tarefas e tempos **abaixo** das metas da entrega 8. A satisfação (4,6) e a compreensão explícita do papel da IA (5,0 na afirmação 4) indicam que o discurso de **estimativa** e a página **Sobre** estão alinhados ao uso responsável pretendido — com ressalvas de generalização pelo perfil especialista do participante.

### Relação com a avaliação heurística (entrega 13)

| Resultado do teste | Implicação |
| :--- | :--- |
| Comentários que **confirmam** V01, V03, V04, V05 (parcial) e V08 | Inspeção heurística bem calibrada; priorizar correções **P0/P1** já listadas |
| **V02**, **V06**, **V07** não acionados no roteiro | Não implicam ausência de problema — fora do escopo das tarefas ou do cenário sem falha |
| Elogios a **B01**, **B02**, **B03**, **B04**, **B06** | **Preservar** no reprojeto |
| Nenhum problema novo fora de V01–V08 | Não foi necessário abrir V09 nesta rodada |

Três comentários espontâneos do participante (**fila sem ETA**, **contraste real/IA**, **CSV sem dicionário**) confirmam diretamente achados da entrega 13, validando a qualidade da inspeção antes do teste.

---

## Problemas prioritários para reprojeto

| Prioridade | Problema (evidência P1) | Violação | Correção proposta |
| :-: | :--- | :-: | :--- |
| 🟡 Média | Fila de processamento sem ETA ou mensagem honesta “sem estimativa” | **V01** | Barra ou texto de status com tempo estimado **ou** aviso explícito quando o *backend* não fornecer ETA |
| 🟡 Média | Camadas **real** e **IA** pouco distinguíveis no tema escuro | **V03** | Legenda fixa + padrão gráfico distinto (cor sólida vs tracejado, ícones) testado em contraste WCAG AA |
| 🟡 Média | Colunas do **CSV** sem glossário na mesma tela | **V04** | Painel “Dicionário de colunas” ou *modal* a partir de **Relatórios** |
| 🟢 Baixa | Métricas de *gaze* sem ajuda contextual até *hover* | **V08** | *Tooltips* persistentes ou link para glossário em **Minha análise** |
| 🟢 Baixa | Termos agregados em **Administração** opacos a não especialistas | **V05** | Glossário por campo ou *tooltips* na visão admin |

### Encadeamento com a síntese heurística (P0–P1)

| ID | Correção (resumo) | Confirmado no teste? |
| :-: | :--- | :--- |
| **V04** | Dicionário de colunas do CSV na mesma vista | ☑ **Sim** (P1, T4) |
| **V07** | Mensagens de erro específicas | ☐ **Não testado** (upload sem falha) |
| **V03** | Legenda fixa e codificação visual distinta real vs IA | ☑ **Sim** (P1, T3) |
| **V01** | ETA ou mensagem “sem estimativa” na fila | ☑ **Sim** (P1, T2) |

---

## Problemas não encontrados no teste

Conforme Barbosa e Silva (2010), a ausência de problemas em determinado escopo **não garante** alta qualidade global — indica apenas que o estudo não os revelou **naquele escopo** com o participante avaliado.

| ID | Motivo de não ter surgido |
| :-: | :--- |
| **V02** | Participante experiente; textos longos não bloquearam T1–T2 |
| **V06** | Roteiro não incluiu cancelamento ou ações destrutivas |
| **V07** | Nenhuma falha de formato/rede foi provocada na sessão |

---

## Limitações metodológicas

- [x] Amostra pequena (*n* = 1 &lt; 5)  
- [x] Participante com conhecimento prévio do projeto (orientador)  
- [x] Protótipo com processamento **simulado** (sem *backend* final)  
- [x] T5 aplicada ao mesmo participante (perfil pesquisa, não motorista leigo)  
- [x] Ausência de teste com motoristas reais pós-viagem em trânsito  

**Recomendação:** em iterações futuras do TCC ou produto, repetir o protocolo com **4–6** participantes externos, incluindo pelo menos **dois** perfis próximos à persona Gustavo, sem conhecimento prévio do código.

---

## Próximos passos

1. Implementar correções **P0** (V04, V07 *templates*) e **P1** (V01, V03) no `bvrai-interface`, referenciando IDs **V** nos *commits*.  
2. Opcional: segunda rodada reduzida (*n* = 2–3) após reprojeto.  
3. Entrega 14 marcada como **concluída** no [README](../../README.md).

---

*Referências: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010. | NIELSEN, J. **Usability Engineering**. Academic Press, 1993.*
