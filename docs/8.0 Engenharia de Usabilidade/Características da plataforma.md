# Características da plataforma

Esta etapa organiza decisões de projeto segundo o ciclo de **Mayhew** (Barbosa e Silva, 2010): descrição do sistema, capacidades, restrições técnicas e, em arquivo complementar, **restrições contextuais e humanas** do uso do BVRAI.

---

## 1. Descrição de software e hardware

| Característica | Descrição |
| :--- | :--- |
| **Tipo de sistema** | Aplicação **web** acessada por navegador; uso previsto em **ambiente controlado**, após a gravação do vídeo (análise pós-evento). |
| **Camadas** | Interface (apresentação), serviços de aplicação (API REST), fila de jobs de processamento de vídeo/IA e **camada de persistência** em banco relacional. |
| **Stack de interface** | HTML5, CSS3, JavaScript; comunicação com *backend* via HTTP/JSON. |
| **Stack de processamento** | Python, *pipelines* de visão computacional e aprendizado de máquina / *deep learning* para extração de atenção visual e inferência. |
| **Banco de dados** | **MySQL** (ou equivalente relacional) para contas, metadados de vídeos, status de processamento, permissões, logs operacionais e referências a arquivos de mídia e relatórios. |
| **Analítica complementar** | Uso previsto de **Power BI** (ou similar) sobre dados agregados exportados ou vistas materializadas, para painéis de gestão. |
| **Sistema operacional do cliente** | Principalmente Windows e macOS em notebooks; navegadores Chromium, Firefox ou Safari em versões recentes. |
| **Hardware típico do usuário** | Notebook ou desktop com tela **≥ 1366×768**; **16 GB RAM** recomendados quando o processamento ocorrer na mesma máquina do operador; **GPU** desejável para acelerar inferência local ou em estação de trabalho dedicada. |
| **Rede** | Conexão estável para **upload** de arquivos de vídeo (ordem de centenas de MB a vários GB por sessão). |
| **Entrada principal** | Arquivos de vídeo (câmera de bordo, *dashcam* ou laboratório), selecionados **fora** do momento da condução na interface. |

---

## 2. Capacidades da plataforma

| Capacidade | Justificativa |
| :--- | :--- |
| **Upload com modo treino ou predição** | Reduz erro de uso ao separar finalidades distintas (ajuste do modelo ao motorista *versus* inferência sobre novo vídeo). |
| **Fila e status de processamento** | Processamento de vídeo/IA é assíncrono; o usuário precisa de visibilidade de etapa, falha e reprocessamento. |
| **Dashboard individual (real × IA)** | Núcleo do valor percebido: comparação entre atenção observada no vídeo e saída do modelo associado ao usuário. |
| **Relatórios exportáveis (PDF / CSV)** | Atende condutor (leitura sintética), frota (planilha e auditoria) e pesquisa (dados tabulares). |
| **Painel administrativo** | Agrega uso, falhas de *pipeline* e volumetria para operação e produto. |
| **Perfis de acesso (motorista / administrador)** | Limita escopo de dados e ações conforme papel, alinhado à minimização e à necessidade de saber (*need to know*). |
| **Persistência auditável** | Metadados e eventos gravados no banco permitem reconstruir **quem** acessou **o quê** e **quando**, em suporte à conformidade e à análise de incidentes. |

---

## 3. Restrições da plataforma (técnicas e de domínio)

| Restrição | Justificativa |
| :--- | :--- |
| **Latência e custo computacional** | Extração de quadros, rastreamento e inferência são intensivos; o tempo de resposta da IA **não** é controlado só pela interface. |
| **Tamanho e formato de vídeo** | *Codecs*, taxa de bits e duração impactam taxa de sucesso do *pipeline*; a UI deve comunicar limites antes do envio. |
| **Qualidade da captura** | Iluminação, ângulo da câmera e estabilidade influenciam a confiança das métricas; resultados devem ser apresentados com **intervalo ou nota de incerteza** quando aplicável. |
| **Dependência de serviços externos** | Se houver APIs de terceiros ou filas na nuvem, indisponibilidade ou *throttling* afeta o fluxo; desenhar mensagens de degradação e retentativa. |
| **Consistência eventual** | Após upload, o estado “processando” pode persistir minutos ou mais; o usuário não deve interpretar atraso como perda de dados sem confirmação no banco. |
| **Ambiguidade semântica da “atenção visual”** | O sistema estima *proxy* de atenção a partir de vídeo; a interface não deve sugerir precisão clínica ou legal além do que o modelo suporta. |
| **Armazenamento de dados sensíveis** | Vídeo e inferências podem ser **dados pessoais sensíveis**; o desenho do banco, *backups* e acessos administrativos são restrições de arquitetura e de política, não só de UI. |

---

## 4. Restrições contextuais e humanas

O detalhamento em formato de análise de **contexto de uso** (carga cognitiva, emoção, ambiente físico e pressões organizacionais) está em:

**[Restrições contextuais e humanas](./Restrições%20contextuais%20e%20humanas.md)**

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
