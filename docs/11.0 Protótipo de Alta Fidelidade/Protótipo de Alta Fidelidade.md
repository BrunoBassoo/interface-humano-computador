# Protótipo de Alta Fidelidade

**Status:** a fazer — capturas de tela e figuras serão inseridas nesta entrega.

Protótipo operacional em navegador (`bvrai-interface`); a documentação abaixo descreve o conteúdo de cada tela até inclusão das imagens.

## Tela 01 — Autenticação
<img width="1657" height="961" alt="login" src="https://github.com/user-attachments/assets/d4ad2355-115e-4683-aa08-3a7032ac1762" />

#### Decisões de design aplicada

* **Identidade institucional imediata e controle de acesso:** Exibição clara do logo e nome do sistema (*BVRAI - Behavioral Visual Replicating AI*) com a tag identificadora de "PROTÓTIPO TCC • FEI • CC8122". Isso atende à restrição de conformidade e ao requisito de **Perfis de acesso**, garantindo que o operador saiba exatamente em qual ambiente acadêmico/institucional está se autenticando.
* **Restrição de domínio por e-mail institucional:** O campo de texto exibe o *placeholder* `seu.email@fei.edu.br`. Essa é uma decisão de design voltada para a **Prevenção de Erros**, indicando visualmente que a plataforma é restrita a membros autorizados da instituição, mitigando tentativas de login com contas pessoais.
* **Minimização da Carga Cognitiva (Lei de Hick):** Formulário estritamente minimalista centralizado em card de alto contraste. Apenas os campos essenciais (E-mail e Senha) e um botão de ação primária em verde-ciano de alta variância cromática, eliminando distrações e focando a tomada de decisão do usuário.
* **Checkbox "Manter conectado" e Link de Recuperação:** Elementos posicionados logo abaixo dos campos de entrada que respeitam a flexibilidade e eficiência de uso, permitindo que usuários frequentes em **notebooks corporativos/pessoais** evitem a fadiga de reinserção de credenciais a cada sessão.

## Tela 02 — Início
<img width="1666" height="795" alt="inicio" src="https://github.com/user-attachments/assets/fabbbd65-06de-4f90-aa96-f75357ad4996" />

#### Decisões de design aplicada

* **Arquitetura de Informação orientada ao status do banco:** Apresentação de um painel de blocos (*cards* de métricas) na parte superior (`7 Participantes`, `18 Vídeos cadastrados`, `9/9 Treino/Predição`). Essa decisão resolve diretamente a restrição de **Consistência Eventual**, permitindo que o operador visualize o estado atualizado do banco relacional (MySQL) instantaneamente ao entrar na plataforma.
* **Visibilidade do Status do Sistema (Heurística de Nielsen):** Os indicadores `18 CSVs de fixações no cache` e `18 Vídeos no cache local` informam ao usuário se os arquivos pesados (ordem de megabytes a gigabytes, conforme a restrição de rede) já foram baixados do Google Drive para o disco da máquina de processamento, mitigando a ansiedade sobre latência de download.
* **Divisão de fluxo em um clique:** O card "O que fazer aqui" oferece caminhos diretos e autoexplicativos através de botões com pesos visuais distintos: ação primária em destaque para `Abrir Análise` (foco no core business da plataforma) e ação secundária para `Cadastrar vídeo`.
* **Transparência tecnológica ("Pipeline em 1 frase"):** Um bloco de texto dedicado resume o fluxo técnico (`Vídeo + CSV -> Detectron2 -> Faixas -> Relatório`). Isso nivela o conhecimento do operador sobre a **Ambiguidade semântica da atenção visual**, deixando claro quais etapas de IA estão gerando os dados.

## Tela 03 — Vídeos e fila
<img width="1668" height="845" alt="vídeos" src="https://github.com/user-attachments/assets/c860e6cb-c15b-4465-93af-a70e97ee8482" />

#### Decisões de design aplicada

* **Prevenção de erros no Upload (Modo Treino vs. Predição):** Inclusão de um campo de seleção (*Select*) explícito para o "Tipo" (`Treinamento` ou `Predição`). Essa decisão mitiga diretamente o erro humano de associar vídeos de inferência à fila de ajuste de modelo do motorista, separando os pipelines assíncronos de forma explícita na UI.
* **Instruções contextuais de permissão de rede:** Abaixo dos campos de URL, há o aviso: *"Os arquivos precisam estar como 'Qualquer pessoa com o link pode ver'"*. Uma decisão de design voltada para evitar quebras no pipeline de download do backend devido a restrições de privacidade externas do Google Drive.
* **Inputs estruturados para correspondência de metadados:** Campos dedicados para separar o link do vídeo MP4 e o link do CSV de fixações do Pupil Labs. Isso garante que a consistência relacional seja mantida no MySQL antes mesmo de a fila de processamento Python ser acionada.

## Tela 04 — Análise
<img width="1546" height="886" alt="análise" src="https://github.com/user-attachments/assets/8f41d995-2b9d-4795-aa65-74d5c5cb8606" />

#### Decisões de design aplicada

* **Exibição Síncrona de Caching e Layout Lado a Lado:** Os players de vídeo de `treino` e `predição` são dispostos de forma paralela e horizontal. O texto de suporte avisa que os vídeos rodam direto do cache local, preparando o usuário para o fato de que a reprodução não sofrerá gargalos de rede, viabilizando a análise pós-evento fluida.
* **Filtros encadeados por Participante e Sessão:** Menus suspensos legíveis permitem selecionar o motorista (`P1 — Rafael`) e as datas das sessões de treino e predição correspondentes. Isso reduz a carga de memória do usuário, permitindo alternar rapidamente entre diferentes conjuntos de testes salvos no banco.
* **Diferenciação cromática de contextos (Tags):** Uso de micro-tags coloridas sobre os vídeos (`treino` em verde-escuro e `predição` em marrom-alaranjado). Uma decisão de design visual para garantir que o operador nunca confunda o dado real observado com a saída gerada pela IA, reforçando os limites de precisão do sistema.

## Tela 05 — Geração de Relatórios
<img width="1572" height="772" alt="relatórios" src="https://github.com/user-attachments/assets/f98d93df-cd24-4d52-8aa3-965be205a8d8" />

#### Decisões de design aplicada

* **Interface focada em lote e utilidade prática:** Layout limpo com seletores simples focado exclusivamente na tarefa de exportação. O sistema reduz as opções de interface ao mínimo necessário para que o usuário execute a geração do documento sem ruído visual.
* **Comunicação de pré-requisito técnico:** O texto explicativo alerta explicitamente: *"O CSV precisa estar baixado para que as métricas apareçam"*. Isso previne frustrações e erros operacionais, correlacionando o status verificado na tela de Análise com a disponibilidade de dados para o relatório.
* **Apoio a atalhos do sistema operacional do cliente:** Inclusão da dica de comando `Ctrl/⌘+P -> Salvar como PDF` logo acima do botão de ação. Uma decisão que integra a aplicação web nativamente com os comportamentos padrão de navegadores (Chromium/Firefox/Safari) documentados no ambiente de hardware do usuário.

### Exemplo do relatório
<img width="1663" height="917" alt="relatório-ex" src="https://github.com/user-attachments/assets/94ad0c4b-5b7a-4685-af6e-321d3d9f6b4b" />

#### Decisões de design aplicada

* **Mudança de Tema para Impressão (Tema Claro):** Ao contrário de todo o resto da plataforma que adota o modo escuro, o relatório utiliza fundo branco com textos em alto contraste (preto/cinza escuro). Esta decisão atende à necessidade de **Relatórios exportáveis legíveis**, economizando tinta em impressões físicas e facilitando a leitura de documentos PDF em monitores comuns de escritórios ou frotas.
* **Cabeçalho de Auditoria e Rastreabilidade:** Exibição explícita de metadados como `ID do relatório (RPT-P1-76GD22)`, `Data do envio` e `Relatório gerado em`. Isso cumpre o requisito de **Persistência auditável**, garantindo conformidade analítica e permitindo reconstruir cronologicamente quando os dados foram processados e emitidos.
* **Card de Avaliação Sintética em Destaque:** O bloco verde com uma nota em destaque (`A - Avaliação orientativa: Padrão de atenção sustentado e bem distribuído`) traduz a complexidade dos dados de IA para uma linguagem acessível para gestores de frota, mitigando a **Ambiguidade semântica da atenção visual** por meio de uma classificação qualitativa clara baseada na literatura.

## Tela 06 - Sobre
<img width="1397" height="772" alt="about" src="https://github.com/user-attachments/assets/5c7a8ace-c93b-4bc6-b013-23d718d2fbd6" />

#### Decisões de design aplicada

* **Explicitação Didática do Pipeline Técnico (Diagrama de Fluxo):** A interface apresenta um diagrama em blocos sequenciais e conectados por setas direcionais (`Entradas -> Detectron2 -> Faixas -> Relatório`). Esta decisão reduz drasticamente a carga cognitiva do operador ao destrinchar visualmente as etapas do *backend* em Python, permitindo que ele compreenda a lógica de processamento síncrono/assíncrono sem precisar ler documentações densas.
* **Ancoragem Institucional e Contexto Acadêmico:** Exibição destacada no topo da descrição do projeto (`FEI, CC8122, orientação acadêmica Victor Varela`). Esta escolha de design textual reforça a governança, a transparência e a autoria do protótipo de TCC / IHC, situando novos pesquisadores ou avaliadores sobre o escopo e as responsabilidades científicas do sistema.
* **Mitigação da Ambiguidade Semântica por meio do Bloco de Correlação:** A inclusão do bloco tracejado `Correlação (onde olha vs. o que está na cena)` conectado diretamente ao `Relatório` serve como uma justificativa visual do modelo. Ela explica graficamente ao usuário que a "atenção visual" estimada não é telepática ou puramente clínica, mas sim o cruzamento matemático entre as coordenadas do Pupil Labs e a detecção de objetos do Detectron2.
* **Transparência da Carga Computacional e Latência:** Ao quebrar o processamento em subetapas visíveis (Detecção de objetos na cena via Detectron2 e Detecção de retas/curvas nas faixas), a UI prepara psicologicamente o operador para o tempo que o sistema levará na fila de processamento. Sabendo que há duas camadas pesadas de visão computacional agindo sobre o vídeo MP4, o usuário compreende por que o estado de "processando" pode persistir por alguns minutos.

## Síntese de Conformidade com as Entregas Anteriores

# Síntese de Conformidade e Engenharia de Usabilidade

Esta matriz documenta de ponta a ponta a rastreabilidade entre as tarefas do sistema **BVRAI**, as modelagens analíticas de IHC (**HTA, GOMS, CTT**), as diretrizes do ciclo de **Mayhew** e a efetiva implementação de alta fidelidade contida no protótipo (`index.html`).

## Matriz de Rastreabilidade Baseada no Ciclo de Mayhew

| ID | Fluxo / Tela do Protótipo | Elemento de Interface (`index.html`) | Modelagem Analítica Aplicada (HTA / GOMS) | Relações de Tarefa Sistemática (CTT) | Diretrizes e Restrições de Plataforma (Mayhew) | Status |
| :---: | :--- | :--- | :--- | :--- | :--- | :---: |
| **01** | **Login**<br>(`login.jpg`) | Campo de texto com o *placeholder* descritivo `seu.email@fei.edu.br`. | **Prevenção de Erros:** Restringe o escopo de entrada visual antes da validação em banco. | **Ativação Inicial:** Bloqueia as tarefas concorrentes até a resolução do nó raiz de login. | **Perfis de Acesso:** Garante a segmentação prévia do papel operando no MySQL (*Motorista* vs. *Admin*). | **OK** |
| **02** | **Início**<br>(`inicio.jpg`) | Cards numéricos superiores de cache de vídeos e arquivos CSV. | **HTA (Tarefa 2):** Fornece visibilidade imediata e controle sobre o status do sistema. | **Leitura Paralela :** Dados de volumetria agregados e carregados de forma síncrona. | **Consistência Eventual:** Sinaliza se os arquivos pesados estão em disco local, mitigando a latência de rede. | **OK** |
| **03** | **Vídeos**<br>(`vídeos.jpg`) | Grupo de botões radiais (`radio-group`) para *Treinamento* ou *Predição*. | **GOMS (Selection Rules):** Ramificação lógica e mandatória dependendo da meta ativa do usuário. | **Escolha Exclusiva (`[]`):** Impede a ativação mútua e concorrente dos dois pipelines de IA. | **Capacidades da Plataforma:** Mitiga a falha operacional de misturar o ajuste do modelo com inferência nova. | **OK** |
| **04** | **Vídeos**<br>(`vídeos.jpg`) | Lista de jobs assíncronos estilizados com as classes `.pill-ok`, `.pill-run` e `.pill-queue`. | **HTA (Tarefa 4):** Monitoramento visual contínuo do ciclo de vida da fila de processamento. | **Tarefa Interativa Iterativa (`*`):** O usuário acompanha as atualizações de estado do job sob demanda. | **Fila de Jobs (Python):** Dá transparência ao tempo de inferência computacional das redes profundas (YOLO/Detectron2). | **OK** |
| **05** | **Minha Análise**<br>(`análise.jpg`) | *Checkboxes* independentes para controlar a renderização das camadas de dados. | **HTA (Rec. 3.2):** Controle granular para evitar a sobreposição excessiva de vetores e fadiga visual. | **Alternância Dinâmica:** Habilita e desabilita os mapas de atenção concorrentes na área do canvas. | **Ambiguidade Semântica:** Separa explicitamente o olhar real registrado do modelo predito pela inteligência artificial. | **OK** |
| **06** | **Minha Análise**<br>(`análise.jpg`) | Painel de exibição lado a lado de métricas: *“0,42 s (usuário) · 0,38 s (IA)”*. | **GOMS (GOAL 2):** Confronto direto de métricas de temporização cognitiva e fixação. | **Sincronismo Interativo :** Renderização em paralelo das saídas estruturadas de atenção pós-evento. | **Dashboard Individual:** Entrega o núcleo de valor analítico e prático definido nos requisitos do projeto. | **OK** |
| **07** | **Relatórios**<br>(`relatórios.jpg`) | Bloqueio dinâmico do seletor `#rel-user` para o nível de privilégio `user`. | **GOMS (GOAL 1):** Restrição automática de escopo de busca baseada na identidade ativa. | **Sequência Rígida (`>>`):** O preenchimento linear impede acessos e vazamento de dados de terceiros. | **Dados Pessoais Sensíveis:** Aplicação estrita do princípio de *Need to Know* e proteção de privacidade (LGPD). | **OK** |
| **08** | **Relatórios**<br>(`relatórios.jpg`) | Gatilhos de exportação e dicas de atalhos de sistema (`Ctrl/⌘ + P`). | **HTA (Tarefa 3):** Fornece opções de saída adaptadas ao objetivo final do usuário. | **Fator de Despacho (`>>`):** Conclusão do fluxo com a geração e transferência do artefato final. | **Analítica Complementar:** O formato CSV é formatado estruturalmente para ingestão no Power BI da gestão de frotas. | **OK** |
| **09** | **Sobre**<br>(`about.jpg`) | Diagrama conceitual em blocos ilustrando o encadeamento dos modelos de visão. | **Minimização de Carga:** Traduz jargões técnicos em um modelo mental digerível para o operador. | **N/A:** Fluxo puramente informativo e de suporte cognitivo, sem alteração de estado no banco. | **Descrição de Hardware/Software:** Justifica a latência explicando a atuação do *Detectron2* e do LSTM no backend. | **OK** |



## Comparativo de Rastreabilidade: Média vs. Alta Fidelidade

Esta tabela apresenta a evolução do sistema **BVRAI** focando em "O que estava na tela" comparado com "Como evoluiu", eliminando jargões técnicos complexos e destacando os ganhos em Interação Humano-Computador (IHC).

### Tabela Comparativa de Evolução da Interface

| Tela do Sistema | Como estava na Média Fidelidade (`index.html`) | Como evoluiu na Alta Fidelidade (Imagens Finais) | O que mudou para melhorar a experiência do usuário (IHC) |
| :--- | :--- | :--- | :--- |
| **01. Login** | Tela escura simples com campos de usuário/senha básicos e uma caixa de texto com dados de teste. | Tela com visual limpo, logo destacado do projeto e um menu sutil de troca de idioma (PT/EN). | **Foco na tarefa:** Removeu-se as informações de teste, criando um formulário minimalista que evita distrações e erros de digitação. |
| **02. Tela Inicial** | Exibia cartões textuais simples que mudavam dependendo de quem fazia o login (Motorista ou Administrador). | Painel unificado com cartões horizontais de resumo (`Participantes`, `Vídeos`, `Fila`) e botões grandes de ação. | **Visibilidade do status:** O usuário agora enxerga de imediato a quantidade de arquivos salvos e o andamento geral do sistema logo ao entrar. |
| **03. Envio de Vídeos** | Lista simples com campos empilhados e botões de seleção comuns para escolher o tipo de processamento. | Formulário organizado verticalmente, integrando a seleção de dados do motorista com a zona de envio de arquivos. | **Prevenção de erros:** A organização mais limpa impede que o operador confunda ou misture arquivos de calibração com vídeos novos. |
| **04. Tela de Análise** | Simulação visual de mapas com círculos coloridos estáticos e degradês feitos por código. | Dois players de vídeo reais rodando lado a lado (Visão do motorista vs. Mapa de predição gerado pela IA). | **Garantia de valor:** Permite a comparação real pós-evento (objetivo central do sistema) de forma clara, usando etiquetas coloridas para diferenciar o usuário da IA. |
| **05. Relatórios** | Formulário com filtros comuns de data e seleção de usuário para abrir uma página de texto em uma nova aba. | Card centralizado e direto, com instruções claras para salvar o documento em formato PDF ou exportar em planilha. | **Eficiência:** Simplificou o processo de exportação e mudou o relatório para o **Tema Claro**, facilitando a leitura em papel impresso ou arquivos digitais. |
| **06. Tela Sobre** | Uma listagem simples em tópicos de texto com os nomes dos integrantes e orientadores da FEI. | Um diagrama visual em blocos que desenha o caminho do vídeo até a geração do relatório final. | **Redução de carga mental:** Substituiu textos longos por um fluxo gráfico simples, ajudando qualquer pessoa a entender como o sistema funciona em segundos. |
