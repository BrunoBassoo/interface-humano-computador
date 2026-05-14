# Síntese e priorização de correções

Este documento **consolida** os achados de [Violações e riscos](./Violações%20e%20riscos.md) num plano de **reprojeto** acionável. A priorização combina **severidade** Nielsen (1994), **impacto** no usuário final (motorista, administrador, pesquisa) e **esforço** estimado de implementação no protótipo estático ou num *backend* futuro — critério habitual em inspeções formativas (Barbosa e Silva, 2010).

## Critérios de priorização

| Dimensão | Pergunta orientadora |
| :--- | :--- |
| **Severidade** | O problema impede conclusão da tarefa, induz erro irreversível ou compromete confiança na IA/dados? |
| **Frequência** | Ocorre em cada sessão, só em casos extremos ou só em determinado perfil (motorista vs admin)? |
| **Dependências** | Corrigir antes do [teste com usuários](../12.0%20Planejamento%20da%20Avaliação%20DECIDE/Planejamento%20da%20avaliação%20DECIDE.md) (Entrega 14)? |
| **Esforço** | Alteração de *copy*/CSS vs novo componente vs contrato de API/exportação? |

## Matriz impacto × esforço (resumo)

| Quadrante | Significado | IDs típicos | Ação |
| :--- | :--- | :--- | :--- |
| **Alto impacto · baixo esforço** | Ganho rápido | V02 (*copy* e hierarquia), V07 (mensagens de erro mais específicas), V08 (tooltips pontuais) | **P0 —** incluir na primeira vaga de correções. |
| **Alto impacto · alto esforço** | Estratégico | V01 (feedback temporal fiável), V04 (dicionário CSV + possível *endpoint*), V03 (redesign de camadas) | **P1 —** fatiar em entregas; validar com orientador. |
| **Baixo impacto · baixo esforço** | Higiene | Pequenos ajustes de contraste, alinhamento de rótulos | **P2 —** *backlog* contínuo. |
| **Baixo impacto · alto esforço** | Evitar por agora | Refinos cosméticos sem ligação a tarefa crítica | **P3 —** adiar pós-TCC ou versão 2. |

## Lista priorizada (síntese das violações)

1. **P0 — Comunicação e prevenção imediata**  
   - **V04:** documentar colunas do CSV **na mesma vista** ou modal (ligação a arquivo/dicionário).  
   - **V07:** *templates* de erro por causa (formato, rede, servidor).  
   - **V02:** reduzir peso visual do texto longo na primeira visita (progressive disclosure, “Ler mais”).  

2. **P1 — Estado do sistema e clareza comparativa**  
   - **V01:** estados de fila com estimativa ou, no mínimo, mensagem honesta “sem ETA” + link **Sobre** técnico.  
   - **V03:** legenda fixa + padrão gráfico distinto (cor, tracejado, ícone) para **real vs IA**; testar contraste WCAG AA onde possível.  
   - **V06:** rever fluxos de cancelamento e confirmações críticas.  

3. **P2 — Profundidade e admin**  
   - **V05:** glossário de termos técnicos na **Administração** ou *tooltip* por campo.  
   - **V08:** expandir ajuda contextual nas métricas menos óbvias.  

4. **Evolução dependente de *backend***  
   - Métricas reais de tempo de processamento para calibrar **V01** e textos de espera (alinhado ao ponto 4 do documento original de síntese).

## Encadeamento com o restante da entrega 13

- Os itens **P0** e parte de **P1** devem estar refletidos no **relato** da Entrega 14 como “correções já aplicadas” ou “em andamento”, para o teste com usuários medir o protótipo **atualizado**.  
- Manter **rastreabilidade**: cada linha de código ou *copy* alterada referencia o ID (V01–V08) na *pull request* ou no relatório do grupo.

---

*Referências: NIELSEN, J. **Enhancing the explanatory power of usability heuristics**. Proc. CHI, 1994. | BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
