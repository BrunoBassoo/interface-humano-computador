# Boas práticas identificadas

Durante a inspeção heurística, registraram-se também **pontos fortes** da interface — elementos que **atendem ou excedem** expectativas em relação às mesmas heurísticas usadas para as violações. Listá-las explicitamente evita reprojeto “cego” que apague comportamentos desejáveis e serve de **referência** para o relatório final (Entrega 14) e para *onboarding* de novos membros da equipe.

## Destaques positivos

| # | Boas prática | Onde aparece | Heurística(s) reforçada(s) | Porque importa |
| :-: | :--- | :--- | :--- | :--- |
| **B01** | **Separação clara de perfis** após o login (motorista vs administrador) | Login · *shell* | H4 (consistência), H2 (modelo mental) | Reduz erro de contexto e permissões inesperadas. |
| **B02** | **Feedback textual imediato** após seleção de arquivo e antes da confirmação de envio | Vídeos | H1 (status), H5 (prevenção) | O usuário sabe que o arquivo foi aceito e pode corrigir antes de submeter. |
| **B03** | **Área dedicada** à comparação **real × IA** com *checkboxes* e camadas sobrepostas | Minha análise | H6 (reconhecimento), H7 (eficiência para usuário experiente) | Centraliza a proposta de valor do BVRAI sem espalhar a comparação por vários menus. |
| **B04** | Página **Sobre** com **escopo acadêmico**, limitações da IA e contexto pós-viagem | Sobre | H10 (ajuda), ética de comunicação | Ancoragem explícita do discurso de **estimativa**, alinhada à engenharia de usabilidade e ao DECIDE. |
| **B05** | Navegação por **abas estáveis** no *shell* (Vídeos, Minha análise, Relatórios, Administração) | *Shell* global | H4 (padronização) | Previsibilidade: o usuário aprende um mapa mental único para motorista e admin. |
| **B06** | **Relatórios** com intervalo de datas e formatos **PDF/CSV** explicitamente oferecidos | Relatórios | H7 (atalhos para necessidade recorrente), H2 (vocabulário de domínio) | Apoia o fluxo de pesquisa e frota sem esconder a exportação em menus profundos. |
| **B07** | Estados de fila **nomeados** (ex.: na fila, a processar, concluído), mesmo que melhoráveis no tempo estimado | Vídeos · listagens | H1 (visibilidade) | Já comunicam diferença de fase em relação a um único “a carregar” genérico. |

## Como usar esta lista no reprojeto

- **Preservar** padrões visuais e de *copy* associados a B01–B07 ao refatorar telas adjacentes (ex.: não mover “Sobre” para um menu oculto ao corrigir V02).  
- Nos **testes com usuários**, incluir perguntas de confirmação: “O que mais lhe deu confiança?” — as respostas tendem a correlacionar com estas práticas.  
- Em apresentações ao orientador, contrastar **uma violação (Vx)** com a **boa prática (By)** da mesma tela para mostrar diagnóstico equilibrado.

---

*Referências: NIELSEN, J. **Enhancing the explanatory power of usability heuristics**. Proc. CHI, 1994. | BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
