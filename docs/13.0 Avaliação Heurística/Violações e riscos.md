# Violações e riscos

A tabela abaixo regista **violações potenciais** ou **riscos de usabilidade** identificados na inspeção heurística do protótipo **BVRAI** (`bvrai-interface`), mapeando cada achado às **10 heurísticas de Nielsen (1994)** e a uma **severidade sugerida** na escala ordinal 0 (sem problema) a 4 (catastrófico). Os identificadores **V01–V08** alimentam a [Síntese e priorização de correções](./Síntese%20e%20priorização%20de%20correções.md).

## Tabela de violações

| ID | Heurística (Nielsen) | Descrição do problema | Sev. (0–4) | Tela / fluxo |
| :-: | :--- | :--- | :-: | :--- |
| **V01** | **H1 — Visibilidade do estado do sistema** | Em alguns estados de fila, o sistema poderia reforçar **quanto tempo falta** ou, na ausência de métricas do *backend*, comunicar explicitamente que **não há estimativa** — evitando a sensação de bloqueio silencioso. | **2–3** | Vídeos · fila de processamento |
| **V02** | **H8 — Estética e design minimalista** | Textos longos na **primeira visita** competem com a ação principal (envio, seleção treino/predição), aumentando carga cognitiva antes da primeira tarefa concluída. | **1–2** | Entrada · Vídeos · *tooltips* densos |
| **V03** | **H6 — Reconhecimento em vez de memorização** | A diferença visual entre camadas **“real”** e **“IA”** pode ser **sutil** em monitores de baixo contraste ou com *theme* escuro, forçando o usuário a memorizar qual legenda estava ativa. | **3** | Minha análise · sobreposição |
| **V04** | **H5 — Prevenção de erros** | Exportação **CSV** sem **dicionário de colunas** na mesma vista aumenta o risco de interpretação errada em análises quantitativas ou em relatórios externos (frota, jurídico). | **3** | Relatórios · exportação CSV |
| **V05** | **H2 — Correspondência entre sistema e mundo real** | Rótulos técnicos ou de *pipeline* (quando expostos) podem soar **opacos** a motoristas ou gestores sem formação em visão computacional — o vocabulário nem sempre traduz o conceito de “estimativa” vs “medição”. | **2** | Administração · métricas agregadas |
| **V06** | **H3 — Controle e liberdade do usuário** | Ações destrutivas ou dispendiosas (ex.: reenvio em massa, limpeza de sessão) podem carecer de **segundo passo de confirmação** ou de *undo* claro, se forem introduzidas em versões futuras. | **2–3** | Administração (evolutivo) |
| **V07** | **H9 — Ajuda a reconhecer, diagnosticar e recuperar de erros** | Mensagens de erro **genéricas** (“algo correu mal”) não orientam correção (formato de vídeo, rede, *timeout*), prolongando tentativas aleatórias. | **2–3** | Vídeos · API simulada |
| **V08** | **H10 — Ajuda e documentação** | Métricas e gráficos na área de análise podem carecer de **ajuda contextual** (*tooltip* ou link para glossário) para termos de atenção *gaze* ou *heatmap*. | **2** | Minha análise · gráficos |

## Riscos transversais (além da heurística)

| Risco | Ligação aos achados | Mitigação sugerida |
| :--- | :--- | :--- |
| **Confiança excessiva na IA** | V03, V05 | Reforçar *copy* e *visual encoding* de “estimativa”; manter coerência com a página **Sobre** (boa prática B04) e com o planejamento **ético** do DECIDE. |
| **LGPD e dados de vídeo** | V04, V07 | CSV e mensagens de erro não devem vazar identificadores sensíveis em ambientes de demonstração; revisar textos antes de produção. |
| **Dois perfis, duas expectativas** | V01, V05 | Priorizar mensagens distintas ou *layouts* para **motorista** vs **admin** quando o mesmo componente servir os dois papéis. |

## Severidade: como interpretar neste projeto

| Grau | Significado operacional no BVRAI |
| :--- | :--- |
| **0–1** | Cosmético ou *nice-to-have*; não bloqueia tarefas do [planejamento DECIDE](../12.0%20Planejamento%20da%20Avaliação%20DECIDE/Planejamento%20da%20avaliação%20DECIDE.md). |
| **2** | Atrito real; o usuário conclui com hesitação ou ajuda informal. |
| **3** | Bloqueio frequente, erro de interpretação de dados ou risco reputacional/legal **plausível** após uso intensivo. |
| **4** | Uso inseguro ou impossibilidade de concluir fluxo crítico sem *workaround* (não identificado como atual no protótipo, mas mantido como teto da escala). |

---

*Referências: NIELSEN, J. **Enhancing the explanatory power of usability heuristics**. Proc. CHI, 1994. | BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
