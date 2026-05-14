# Metas de usabilidade

As metas traduzem os requisitos de usabilidade em critérios verificáveis (eficácia, eficiência e satisfação), incluindo aspectos ligados à **confiança na IA** e à **transparência do tratamento de dados** persistido no servidor.

---

## Metas qualitativas

| Meta | Descrição |
| :--- | :--- |
| **Aprendizado em uma sessão** | Primeiro fluxo de **predição** (login → upload → visualização de resultado resumido) concluível sem manual impresso, apenas com textos e *tooltips* da interface. |
| **Linguagem inclusiva** | Telas voltadas ao motorista evitam siglas opacas de modelo (*LSTM*, nome interno de *checkpoint*, etc.) sem definição acessível. |
| **Recuperação de erro** | Falhas de rede, formato ou limite de tamanho produzem mensagens com **causa provável** e **próximo passo** (reenviar, comprimir, contatar suporte). |
| **Rastreabilidade administrativa** | Filtros e listagens permitem localizar falhas de processamento e correlacionar com identificador de *job* ou registro no banco. |
| **Transparência de dados** | O usuário identifica **quais dados** são mantidos após o envio, por quanto tempo (em linha com a política) e como solicitar exclusão ou exportação, quando aplicável. |
| **Alinhamento UI–persistência** | Estados exibidos (“processando”, “concluído”) refletem registros no **MySQL**, reduzindo sensação de perda de arquivo após recarregar a página. |

---

## Metas quantitativas iniciais (a validar na avaliação formal)

| Indicador | Meta inicial | Comentário |
| :--- | :--- | :--- |
| Taxa de conclusão do fluxo motorista (login → upload → visualização) | ≥ 80 % | Teste com usuários ou registro de funil anonimizado |
| Tempo até primeira métrica legível (excluindo processamento da IA) | ≤ 4 min | Apenas interação na interface |
| Satisfação pós-tarefa (Likert 1–5) | ≥ 3,8 | Questionário curto ao fim de tarefa representativa |
| Erros críticos de interpretação (“IA = laudo definitivo”) após leitura da tela | ≤ 10 % | Pergunta fechada de verificação de compreensão |
| Taxa de sucesso de primeiro upload sem erro de formato/tamanho | ≥ 85 % | Depende de validação pré-envio e comunicação de limites |

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
