# Restrições contextuais e humanas

Além das restrições técnicas, o ciclo de Mayhew prevê a análise do **contexto de uso**: condições ambientais, cognitivas, emocionais e organizacionais em que a pessoa interage com o BVRAI (Barbosa e Silva, 2010). A tabela abaixo consolida implicações de design alinhadas às personas do projeto (condutor, frota, pesquisa, produto).

| Restrição contextual | Impacto no usuário | Implicação para o design |
| :--- | :--- | :--- |
| **Análise pós-viagem, frequentemente à noite ou em horário pessoal** | O condutor pode estar fatigado, com menor tolerância a formulários longos e a jargão técnico; a expectativa é de “resposta clara” sobre o próprio comportamento. | Reduzir decisões por tela (Hick-Hyman); priorizar resumo executivo e linguagem acessível; oferecer modo escuro e hierarquia visual forte para leitura em ambiente com pouca luz. |
| **Carga emocional e medo de julgamento (motorista / frota)** | Resultados de atenção podem ser lidos como “nota de conduta” ou expor o motorista a críticas internas; há ansiedade legítima sobre **uso de vídeo** e interpretação da IA. | Textos curtos sobre **finalidade** e **limites** da análise; evitar tom punitivo; destacar que a IA é **apoio à interpretação**, não decisão automática de política disciplinar; consentimento e transparência visíveis antes do upload. |
| **Atenção dividida no trabalho (gestor de frota, engenharia)** | O usuário alterna entre BVRAI, e-mail, planilhas e chamadas; interrupções são frequentes. | Suportar retomada de fluxo (estado salvo no servidor, mensagens “continuar de onde parou”); listas e filtros estáveis; exportações reproduzíveis; evitar *modais* bloqueantes desnecessários. |
| **Alta densidade de informação (pesquisa)** | Longas sessões diante de métricas, gráficos e exportações; risco de sobrecarga e de erro de interpretação estatística. | Permitir *drill-down* progressivo; documentação embutida ou link estável para dicionário de métricas; CSV com colunas nomeadas de forma consistente com o banco de dados de origem. |
| **Responsabilidade organizacional e rastro de decisão (frota / produto)** | Decisões precisam ser defendidas perante diretoria, jurídico ou cliente; exige **rastreabilidade** e comparabilidade entre períodos. | Painel administrativo com filtros por período e status; mensagens de erro com **código** ou identificador correlacionável a log; exportações com carimbo de tempo e escopo explícito. |
| **Baixa tolerância a espera sem feedback (todos os perfis após upload)** | O processamento demora; silêncio na tela é interpretado como travamento ou perda de arquivo. | Barra ou etapas explícitas; estimativa quando possível; confirmação persistida no banco (“recebido”, “na fila”, “concluído”, “falha”); notificação visual não intrusiva ao concluir. |
| **Ambiente silencioso (escritório / home office)** | Alertas sonoros podem incomodar colegas ou familiares. | Som opcional e desligado por padrão; *toast* ou *badge* visível em aba. |

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
