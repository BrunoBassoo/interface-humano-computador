# Preparação da sessão

Procedimento de preparação do teste com usuários do **BVRAI**, alinhado ao item **I — Identificar questões práticas** do [planejamento DECIDE](../12.0%20Planejamento%20da%20Avaliação%20DECIDE/Planejamento%20da%20avaliação%20DECIDE.md). **Sessão realizada:** 14/05/2026 · P1 · laboratório FEI · OBS + TCLE.

---

## Materiais utilizados

| Instrumento | Função | Onde registrar |
| :--- | :--- | :--- |
| **TCLE** | Consentimento livre e esclarecido antes do início | Conforme política da instituição (entrega 7) |
| **Questionário pré-teste** | Perfil: formação, experiência com *dashboards*, envio de vídeo, familiaridade com IA | [Questionário pós-teste](./Questionário%20pós-teste.md#questionário-pré-teste) |
| **Roteiro de tarefas** | Enunciados entregues ao participante — linguagem de usuário, **sem** instruir cliques | [Tarefas e métricas](./Tarefas%20e%20métricas.md#roteiro-entregue-ao-participante) |
| **Roteiro de observação** | Anotações do moderador: tempo, erros, ajudas, citações | [Registro de eventos](./Registro%20de%20eventos.md) |
| **Questionário pós-teste** | Cinco afirmações em escala Likert (1–5) + pergunta aberta | [Questionário pós-teste](./Questionário%20pós-teste.md) |

---

## Ambiente e equipamento

- Dois computadores com o mesmo *build* do protótipo (`bvrai-interface/index.html` local ou servido em `localhost`).
- Navegador atualizado (Chrome, Edge ou Firefox); resolução mínima **1280×720**.
- Software de gravação de tela e áudio (**OBS Studio** ou equivalente) com consentimento explícito no TCLE.
- Cronómetro ou marcações na gravação para tempos por tarefa.
- Intervalo **≥ 15 min** entre sessões para limpar `sessionStorage` / sessão do navegador.

### Credenciais de demonstração (protótipo)

| Perfil | Usuário | Senha | Uso nas tarefas |
| :--- | :--- | :--- | :--- |
| **Motorista** | `usuario` | `123456` | T1–T4 (fluxo principal) |
| **Administrador** | `admin` | `admin123` | T5 (opcional) |

*Fonte: [`bvrai-interface/README.md`](../../bvrai-interface/README.md).*

---

## Teste-piloto

Antes da primeira sessão formal:

1. Um integrante da equipe **fora** da lista de participantes executa T1–T4 em voz alta.
2. Validar duração total (**meta: 45–60 min** com entrevista).
3. Ajustar redação dos enunciados se houver ambiguidade (“predição” vs “treino”, “Minha análise”, etc.).
4. Confirmar que vídeos de *fixture* ou simulação não exigem upload real de trânsito sem consentimento específico.

---

## Conduta do moderador

- Instruir: dúvidas sobre **o que fazer** são permitidas; dúvidas sobre **como usar o sistema** não devem ser respondidas (exceto se o participante estiver bloqueado por falha técnica não relacionada à usabilidade).
- *Think-aloud* **opcional** — registrar apenas se o participante consentir e se não atrasar demais a sessão.
- Não corrigir cliques durante a tarefa; anotar hesitações e pedidos de ajuda como **erro ou ajuda** na folha de observação.

---

## Checklist pré-sessão (P1 — concluído)

- [x] TCLE impresso ou digital assinado  
- [x] Protótipo aberto e credenciais testadas  
- [x] Gravação configurada e testada (`sessao-P1-victor-varela-20260514.mp4`)  
- [x] Roteiro de tarefas e folha de observação impressos ou em segunda tela  
- [x] Questionários pré e pós-teste prontos  
- [x] Vídeo de demonstração ou modo simulado validado (arquivo de *fixture*, sem vídeo real de trânsito)  

---

*Referências: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010. | Resolução CNS nº 196/96 (ética em pesquisa com seres humanos).*
