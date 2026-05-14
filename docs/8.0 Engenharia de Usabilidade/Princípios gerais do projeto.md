# Princípios gerais do projeto

Conforme Barbosa e Silva (2010), esta etapa reúne normas, boas práticas e referências ergonômicas aplicáveis à concepção da interface, considerando **usuário, tarefa, equipamento e ambiente**. No BVRAI, a existência de **banco de dados relacional (MySQL)** para persistir contas, metadados de vídeos, resultados parciais, permissões e trilhas de uso **amplia** o escopo: a proteção de dados deixa de ser só “texto na tela” e passa a envolver modelo de dados, controle de acesso, *backup*, retenção e registro de operações.

---

## Contexto de uso e tratamento de dados

O sistema é utilizado por **condutores**, **gestores de frota ou segurança veicular**, **pesquisadores** e **equipes de produto/software**, via navegador, em regime de **análise pós-gravação**. Vídeos de direção e inferências sobre padrão de atenção constituem **dados pessoais** e, em muitos casos, **dados sensíveis** (biometria inferida ou hábito de locomoção), nos termos da **LGPD (Lei nº 13.709/2018)**. O banco de dados concentra identificadores, vínculos entre usuário e arquivo, resultados agregados e eventos de auditoria; por isso, princípios de **minimização**, **finalidade**, **integridade**, **confidencialidade** e **transparência** orientam tanto o *schema* quanto a interface (o que é exibido, a quem e por quanto tempo).

---

## Referências incorporadas

| Referência | Descrição e relevância para o BVRAI | Link |
| :--- | :--- | :--- |
| **LGPD — Lei nº 13.709/2018** | Base legal para tratamento de dados pessoais e sensíveis no Brasil. No projeto, o MySQL armazena metadados e resultados: exige **base legal** adequada (consentimento, legítimo interesse com teste de proporcionalidade, ou outra hipótese prevista), **registro de operações** de tratamento, definição de **encargos** (controlador/operador), **resposta a titular** e **notificação** de incidentes quando aplicável. | [Lei 13.709/2018](https://www.planalto.gov.br/ccivil_03/_ato2015-2018/2018/lei/l13709.htm) |
| **Segurança da informação em camadas (defesa em profundidade)** | O *frontend* não expõe credenciais nem *tokens* em texto claro; o *backend* valida sessão; o banco usa **usuário de aplicação** com privilégios mínimos; dados em repouso podem usar criptografia de volume ou de coluna para campos críticos, conforme arquitetura adotada. | Boas práticas OWASP / CIS (referência geral de hardening) |
| **ISO/IEC 27001 / 27701 (como referência de boas práticas)** | Apoio à definição de controles para **gestão de acesso**, **cópias de segurança**, **retenção** e **descarte** alinhados ao risco; útil para comunicação com stakeholders corporativos. | Normas ISO (consulta institucional) |
| **ISO 9241-110** | Adequação à tarefa: fluxos de upload distinguem **treino** e **predição**; rotas administrativas não misturam dados de titulares sem autorização. | ABNT ISO 9241 |
| **WCAG 2.1 (nível AA como meta)** | Contraste, foco visível, rótulos em formulários de login e upload, compatibilidade com leitores de tela nas telas críticas. | [WCAG 2.1 *quick reference*](https://www.w3.org/WAI/WCAG21/quickref/) |
| **Lei de Acessibilidade — Lei nº 10.098/2000** | Critérios gerais de acessibilidade em produtos e serviços no Brasil; reforça compromisso com inclusão na interface web. | [Lei 10.098/2000](https://www.planalto.gov.br/ccivil_03/leis/l10098.htm) |
| **Heurísticas de Nielsen (1994)** | Visibilidade de status da fila, prevenção de erro no envio (tipo/tamanho de arquivo), consistência de termos entre UI, API e colunas exportadas para o CSV. | [Nielsen, 1994](https://www.nngroup.com/articles/ten-usability-heuristics/) |
| **Diretrizes de governança de dados em banco relacional** | Modelagem com chaves estrangeiras e perfis; **auditoria** de `SELECT`/`UPDATE` sensíveis; mascaramento em ambientes de teste; política de **retenção** (quanto tempo vídeo e inferência permanecem armazenados); **anonimização** ou pseudonimização para bases de pesquisa secundárias. | Prática de engenharia de dados alinhada à LGPD |

---

## Implicações específicas do uso de MySQL

| Tema | Princípio adotado no projeto |
| :--- | :--- |
| **Minimização** | Armazenar só campos necessários à operação (ex.: *hash* de arquivo, duração, status), evitando duplicar em tabelas de UI dados que já existem em objeto de armazenamento de mídia. |
| **Segregação de funções** | Papéis de aplicativo distintos para serviço de *upload*, serviço de inferência e relatórios; permissões de leitura/escrita coerentes com perfil motorista *versus* administrador. |
| **Rastreabilidade** | Tabela ou *log* de eventos com carimbo de tempo, identificador de sessão e ação (login, upload, exportação, falha de *job*), sem gravar dados excessivos que violem minimização. |
| **Integridade** | Transações para atualizar status de processamento e metadados de forma consistente; evitar estados “órfãos” percebidos pelo usuário como vídeo sumido. |
| **Confidencialidade** | Conexão cifrada entre cliente e servidor; credenciais do banco fora do repositório; *secrets* em variáveis de ambiente ou cofre. |
| **Retenção e exclusão** | Política documentada: prazo de guarda de vídeo e de inferências; fluxo de exclusão a pedido do titular quando aplicável. |

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
