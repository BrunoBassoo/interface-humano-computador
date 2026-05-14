# Planejamento da avaliação de IHC (DECIDE)

O planejamento segue o acrônimo **DECIDE** (*Determine goals*, *Explore questions*, *Choose methods*, *Identify practical issues*, *Decide ethics*, *Evaluate how to present results*), apresentado por Preece, Rogers e Sharp (2002) e adotado em Barbosa e Silva (2010) como guia para desenhar **avaliações formativas e somativas** antes e depois de testes com usuários. No **BVRAI**, a avaliação foca o protótipo web (`bvrai-interface`), o fluxo vídeo → fila → análise comparativa real × IA e as exportações (PDF/CSV), alinhada às metas da entrega 8.

---

## D — Determinar os objetivos da avaliação

A avaliação do BVRAI visa:

1. **Detectar problemas de interação e de interface** que prejudiquem condutores, administradores de frota ou perfis de pesquisa ao completar tarefas críticas (autenticação, envio, leitura de resultados, exportação).
2. **Verificar conformidade com princípios e normas** relevantes — heurísticas de Nielsen, orientações WCAG nas rotas principais, e coerência com o discurso de **limitação da IA** e de **proteção de dados** (LGPD, tratamento em MySQL).
3. **Avaliar apropriação e confiança** — perceber se usuários sem formação em visão computacional interpretam métricas e *heatmaps* sem atribuir à IA papel de “sentença” sobre conduta ou desempenho legal.
4. **Medir eficácia e eficiência** relativamente às metas quantitativas definidas na engenharia de usabilidade (taxas de conclusão, tempos de interação sem contar o processamento da *pipeline*).
5. **Priorizar correções** para um ciclo de reprojeto documentado (entrega 13 — heurística; entrega 14 — teste com usuários).

---

## E — Explorar as perguntas a serem respondidas

As perguntas derivam dos objetivos acima e orientam o protocolo de coleta de dados.

### Sobre problemas na interação e na interface

- O usuário distingue **treino** e **predição** antes de confirmar o envio, sem hesitação prolongada?
- Os estados **Na fila / Processando / Concluído** reduzem a percepção de “sistema parado” ou de perda de arquivo?
- Os *checkboxes* e a **sobreposição** em “Minha análise” são descobertos e utilizados sem ajuda?
- O fluxo até **Relatórios** (PDF ou CSV) é encontrado sem pista verbal do moderador?

### Sobre conformidade com padrões e clareza da IA

- Que heurísticas de Nielsen são violadas e com que **severidade** (0–4)?
- O texto de **Sobre** e os *leads* das abas reforçam que a análise é **pós-viagem** e em ambiente controlado?
- Os usuários descrevem a camada “IA” como **estimativa** ou como “veredicto” sobre a sua condução?

### Sobre exportação, administração e dados

- Administradores localizam envios falhados e correlacionam com identificador de *job* (quando existir integração com base de dados)?
- A exportação CSV é percebida como útil sem **dicionário de colunas** na mesma tela (risco identificado na heurística)?

### Sobre eficácia e eficiência

- O tempo médio desde o login até a primeira leitura útil em “Minha análise” (excluindo tempo de *GPU*) situa-se abaixo do limiar definido na entrega 8?
- A taxa de conclusão das tarefas scriptadas sem ajuda atinge a meta mínima?
- A satisfação pós-tarefa (Likert 1–5) atinge ou ultrapassa o valor-alvo?

---

## C — Escolher os métodos de avaliação

Utilizam-se **dois métodos complementares** em sequência lógica: primeiro inspeção (baixo custo), depois observação com participantes (custos de recrutamento).

### Método 1 — Avaliação heurística (inspeção)

| Aspeto | Especificação |
| :--- | :--- |
| **Tipo** | Inspeção **sem** usuários finais na sala |
| **Momento** | **Formativa** — antes do teste com usuários, para corrigir problemas óbvios e alinhar vocabulário |
| **Avaliadores** | Membros da equipe do projeto, com lista de verificação baseada nas **10 heurísticas de Nielsen (1994)** e critérios complementares (IA, privacidade, consistência UI ↔ dados persistidos) |
| **Escopo** | Telas do protótipo: login, *shell* com abas, **Vídeos** (motorista e admin), **Minha análise**, **Relatórios**, **Administração**, **Sobre** |
| **Dados gerados** | Qualitativos (descrição do problema) e ordinais (**severidade** 0–4) |
| **Justificativa** | Identifica violações de padrões e inconsistências sem dependência de calendário de recrutamento (Barbosa e Silva, 2010) |

### Método 2 — Teste de usabilidade com tarefas (observação)

| Aspeto | Especificação |
| :--- | :--- |
| **Tipo** | Avaliação com observação e medição em tarefas representativas |
| **Momento** | **Somativa** após correções prioritárias da heurística, quando aplicável |
| **Participantes** | Mistura de perfis próximos das personas (condutor ocasional, usuário com experiência em *dashboards*, perfil técnico); *n* alvo entre **4 e 6** por rodada — compromisso entre custo e cobertura de problemas (Nielsen, 1994, sugere ~5 para grande parte dos problemas de usabilidade) |
| **Dados gerados** | Quantitativos (tempo, erros, conclusão sim/não) e qualitativos (comentários, *think-aloud* opcional, questionário pós-tarefa) |
| **Justificativa** | Único método que expõe diferenças entre quem desenhou e quem usa (Barbosa e Silva, 2010) |

### Métodos auxiliares (opcionais na mesma campanha)

| Método | Papel |
| :--- | :--- |
| **Entrevista breve pós-tarefa** | Esclarecer confiança na IA e preocupações com vídeo e dados |
| **Revisão heurística de acessibilidade** | *Checklist* WCAG 2.1 nos componentes críticos (login, abas, formulários de datas) |

---

## I — Identificar questões práticas

### Perfil dos participantes (teste com usuários)

| Critério | Especificação |
| :--- | :--- |
| **Contexto** | Uso de *sites* e aplicações pelo menos em nível intermediário (autopercebido) |
| **Experiência com vídeo** | Já ter enviado arquivos grandes ou gravado com câmera de bordo (desejável, não obrigatório) |
| **Exclusão** | Membros da equipe de desenvolvimento do BVRAI; quem participou na **definição** do roteiro da sessão em teste |

### Tarefas a realizar (alinhadas ao HTA e aos cenários da entrega 9)

| # | Tarefa | Critério de sucesso |
| :-: | :--- | :--- |
| **T1** | Autenticar como motorista e acessar **Vídeos** | Login concluído sem assistência e aba correta visível em tempo ≤ 1 min |
| **T2** | Selecionar **predição**, anexar arquivo (ou simular) e **confirmar envio** | Estado na lista passa a visível (fila/processamento/concluído) sem erro de formato |
| **T3** | Abrir **Minha análise**, alterar sessão/período e ativar/desativar camadas | Usuário explica verbalmente diferença entre olhar real e IA |
| **T4** | Gerar **PDF** ou **CSV** em **Relatórios** com intervalo de datas válido | Ação concluída ou *download* iniciado conforme implementação |
| **T5** (opcional, perfil admin) | Percorrer **fila global** e **Administração** | Identifica pelo menos um indicador agregado e um estado de envio |

### Equipamento e recursos

- Dois computadores com o mesmo *build* do protótipo (`index.html` local ou servido em `localhost`).
- Software de gravação de tela e áudio com **consentimento** explícito.
- **TCLE** ou roteiro de consentimento verbal + registro de aceitação.
- Questionário pré-teste (perfil) e **pós-teste** (Likert e pergunta aberta sobre confiança na IA).
- Folha de observação com colunas: tempo, erro, ajuda solicitada, citação relevante.

### Ambiente e logística

- Sala silenciosa ou laboratório; sessão **45–60 min** por participante; intervalo entre sessões para **repor** `sessionStorage` / sessão limpa.
- **Teste-piloto** com uma pessoa fora do protocolo formal para validar tempos e formulação das tarefas.

---

## D — Decidir sobre as questões éticas

A avaliação envolve pessoas e, quando gravada, dados pessoais de participação; adotam-se princípios alinhados à **Resolução nº 196/96 do CNS** e à **LGPD**, em consonância com a entrega 7.

| Princípio | Medida |
| :--- | :--- |
| **Autonomia** | Participação voluntária; direito de parar a qualquer momento; esclarecimento prévio dos objetivos |
| **Não maleficência** | Não exigir vídeo real de trânsito sem consentimento específico; usar *fixtures* ou vídeos anonimizados quando necessário |
| **Beneficência** | Resultados destinam-se a melhorar a interface e a documentação do TCC |
| **Confidencialidade e anonimato** | Gravações em repositório restrito da equipe; códigos (P1, P2, …) nos relatórios públicos |
| **Transparência** | Explicar que o protótipo pode não refletir ainda o *backend* final nem a política de retenção definitiva |

### Instrumentos (lista de verificação)

- [ ] TCLE ou equivalente aprovado conforme política da instituição  
- [ ] Questionário pré-teste  
- [ ] Roteiro de tarefas entregue ao participante (se aplicável)  
- [ ] Roteiro de observação para o moderador  
- [ ] Questionário pós-teste  

---

## E — Avaliar, interpretar e apresentar os resultados

### Após a avaliação heurística

- Registrar cada problema na estrutura da **entrega 13**: heurística, descrição, severidade (0–4), tela ou signo afetado.
- Corrigir **antes do teste com usuários** todos os itens com severidade **3** ou **4**, sempre que tecnicamente viável.

### Após o teste com usuários

Consolidação **intra e intersujeto** (Barbosa e Silva, 2010):

| Dado | Tipo | Instrumento |
| :--- | :--- | :--- |
| Tempo por tarefa | Quantitativo | Cronómetro / marcações na gravação |
| Taxa de conclusão | Quantitativo | Roteiro de observação |
| Número de erros / ajudas | Quantitativo | Idem |
| Satisfação (Likert) | Ordinal | Questionário pós-teste |
| Comentários verbalizados | Qualitativo | Transcrição parcial ou notas |

### Relato final (entrega 14)

O relatório deve integrar: objetivos e escopo; perfil dos participantes; síntese quantitativa e qualitativa; lista de problemas por severidade; interpretação; **plano de reprojeto** com priorização (impacto × esforço). A revisão do texto final deve envolver mais do que um membro da equipe, cobrindo os eixos motorista, administração/pesquisa e produto, para reduzir viés de interpretação.

---

*Referências: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010. | PREECE, J.; ROGERS, Y.; SHARP, H. **Interaction Design**. Wiley, 2002.*
