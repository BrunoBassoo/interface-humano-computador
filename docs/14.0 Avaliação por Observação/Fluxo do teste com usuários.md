# Fluxo do teste com usuários

O teste de usabilidade com observação do **BVRAI** segue o planejamento [DECIDE](../12.0%20Planejamento%20da%20Avaliação%20DECIDE/Planejamento%20da%20avaliação%20DECIDE.md) (entrega 12) e ocorre **após** a [avaliação heurística](../13.0%20Avaliação%20Heurística/Avaliação%20Heurística.md) (entrega 13), de preferência com correções **P0** aplicadas quando viável. O desenho visual replica o fluxograma da entrega 14 do projeto de referência (GAIA): preparação → sessão cronometrada → relato dos resultados.

## Fluxograma (gráfico)

![Fluxograma do teste com usuários — BVRAI](./assets/fluxograma-teste-usuarios-bvrai.svg)

*Arquivo editável: [`assets/fluxograma-teste-usuarios-bvrai.svg`](./assets/fluxograma-teste-usuarios-bvrai.svg).*

## Resumo dos passos (texto)

```
PREPARAÇÃO
    │
    ├── Recrutar participantes (perfis próximos às personas — ver Recrutamento)
    ├── Preparar ambiente (bvrai-interface em execução, gravação de tela com consentimento)
    ├── Preparar TCLE, roteiro de tarefas, folha de observação e questionários
    └── Realizar teste-piloto (integrante da equipe, fora do protocolo formal)
          │
          ▼
SESSÃO (~45–60 min)
    │
    ├── 1. Apresentação dos objetivos da avaliação (~5 min)
    ├── 2. Assinatura do TCLE
    ├── 3. Questionário pré-teste (perfil)
    ├── 4. Exploração livre do sistema (~5 min) — opcional
    ├── 5. Execução das tarefas T1–T5 (observação; ajuda só sobre o objetivo, não o “como clicar”)
    ├── 6. Questionário pós-teste (satisfação Likert 1–5)
    └── 7. Entrevista breve pós-teste (esclarecer eventos e confiança na IA)
          │
          ▼
RELATO DOS RESULTADOS
    │
    ├── Consolidar tempos, erros e conclusão por tarefa
    ├── Registrar comentários e correlacionar com violações V01–V08 (entrega 13)
    ├── Comparar com metas da entrega 8
    └── Atualizar plano de reprojeto (Conclusão e reprojeto)
```

## Etapas detalhadas

| # | Etapa | Foco no BVRAI |
| :-: | :--- | :--- |
| 1 | **Preparação** | *Build* do protótipo (`bvrai-interface`), vídeos de demonstração ou *fixtures*, instrumentos éticos (entrega 7). |
| 2 | **Sessão** | Tarefas T1–T5 alinhadas ao HTA e aos cenários da entrega 9; perfil motorista obrigatório; T5 opcional para admin. |
| 3 | **Relato** | Tabelas em [Tarefas e métricas](./Tarefas%20e%20métricas.md), [Registro de eventos](./Registro%20de%20eventos.md) e [Conclusão e reprojeto](./Conclusão%20e%20reprojeto.md). |

## Relação com outras entregas

| Entrega | Contribuição para o fluxo |
| :--- | :--- |
| **12 — DECIDE** | Objetivos, perguntas, métodos, ética, critérios de sucesso T1–T5 |
| **13 — Heurística** | Hipóteses de problemas (V01–V08) a validar ou refutar no teste |
| **8 — Metas** | Limiares de conclusão, tempo e satisfação |
| **6 — Prototipação** | Teste exploratório prévio (Mariana) — **não** substitui esta entrega |

---

*Referências: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010. | NIELSEN, J. **Usability Engineering**. Academic Press, 1993.*
