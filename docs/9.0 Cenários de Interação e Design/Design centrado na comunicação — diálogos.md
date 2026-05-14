# Design centrado na comunicação — diálogos

Tabela de diálogos no estilo **tópico > subtópico** (Barbosa e Silva, 2010). **U** = usuário · **S** = sistema (BVRAI, protótipo `bvrai-interface`).

---

## Acesso e sessão

| Tópico > subtópico | U · S |
| :--- | :--- |
| **Autenticação > envio do formulário** | U: informa usuário e senha e aciona entrar. S: valida credenciais contra regra simulada; em caso positivo, monta cabeçalho com *pill* de perfil e conjunto de abas adequado. |
| **Autenticação > credencial inválida** | U: informa combinação incorreta. S: exibe mensagem de erro em `#login-error`, mantém foco no formulário e não libera `main-app`. |
| **Autenticação > dica de contas de demonstração** | U: lê o texto de ajuda com usuários `usuario` e `admin`. S: apresenta credenciais fictícias apenas para protótipo; em produção seria substituído por fluxo seguro de primeiro acesso. |
| **Sessão > encerrar** | U: clica em **Sair**. S: limpa `sessionStorage`, retorna à tela de login e remove dados sensíveis da memória do cliente. |
| **Sessão > retorno após recarregar página** | U: atualiza o navegador no meio do fluxo. S: depende da persistência adotada; o protótipo orienta re-login — implicação: estados críticos devem estar no servidor/banco para não perder upload concluído. |

---

## Navegação principal (abas)

| Tópico > subtópico | U · S |
| :--- | :--- |
| **Abas > Início** | U: seleciona **Início**. S: exibe mensagem de boas-vindas contextual (motorista *versus* admin), cartões explicativos e estatísticas fictícias. |
| **Abas > Vídeos** | U: seleciona **Vídeos**. S: alterna painel entre visão do motorista (`videos-user`) ou fila global (`videos-admin`) conforme o papel. |
| **Abas > Minha análise** | U: seleciona **Minha análise** (apenas motorista). S: exibe *dashboard* comparativo; para admin a aba permanece oculta. |
| **Abas > Relatórios** | U: seleciona **Relatórios**. S: exibe título e texto de *lead* conforme papel; admin vê escopo ampliado (“qualquer motorista”). |
| **Abas > Administração** | U: seleciona **Administração** (apenas admin). S: mostra KPIs agregados; motorista não vê a aba. |
| **Abas > Sobre** | U: seleciona **Sobre**. S: apresenta escopo acadêmico, limitações da IA e lista de entregas do TCC/IHC. |

---

## Vídeos (motorista)

| Tópico > subtópico | U · S |
| :--- | :--- |
| **Modo de envio > treino** | U: marca **Vídeo para treinamento do modelo**. S: associa metadado `tipo=treino` ao próximo envio (comportamento previsto na integração). |
| **Modo de envio > predição** | U: marca **Vídeo para predição**. S: associa `tipo=predicao` e ajusta expectativa de saída na fila. |
| **Arquivo > seleção** | U: clica em **Escolher arquivo** ou arrasta para a *upload-zone*. S: exibe nome/tamanho previsto do arquivo (comportamento a implementar; protótipo sugere *feedback* imediato). |
| **Arquivo > formato inválido** | U: tenta anexar arquivo não suportado. S: bloqueia **Confirmar envio** e lista extensões aceitas (MP4, etc.). |
| **Envio > confirmar** | U: aciona **Confirmar envio**. S: enfileira *job* (simulado), insere linha em **Meus envios** com estado inicial. |
| **Fila pessoal > progressão de estado** | U: observa a lista **Meus envios**. S: atualiza selos **Na fila** → **Processando** → **Concluído** (ou **Erro** em versão futura). |
| **Fila pessoal > item sem resultado** | U: clica em sessão ainda não concluída esperando análise. S: em integração real, redireciona ou exibe *placeholder* “Aguardando processamento”; protótipo pode apenas listar. |

---

## Vídeos (administrador)

| Tópico > subtópico | U · S |
| :--- | :--- |
| **Fila global > leitura** | U: percorre lista **Todos os envios (recentes)**. S: mostra `usuário · arquivo · pill` de status para cada linha. |
| **Fila global > nota de API** | U: lê o cartão sobre *upload* em nome de terceiro. S: explica que o protótipo não implementa ação, apenas comunica o desenho pretendido da API/painel interno. |
| **Incidente > falha de pipeline** | U: identifica status vermelho ou travado (futuro). S: deve retornar código de erro correlato a registro em **MySQL** e *log* de *job*. |

---

## Minha análise

| Tópico > subtópico | U · S |
| :--- | :--- |
| **Contexto > seleção de sessão** | U: altera o primeiro `<select>` (“Sessão — …”). S: recarrega *heatmaps* e métricas da sessão escolhida (dados *mock*). |
| **Contexto > período agregado** | U: altera o segundo `<select>` (últimos 7/30 dias). S: restringe agregação exibida na barra de métricas. |
| **Camadas > mapa real** | U: mantém **Mapa de atenção real** marcado. S: exibe painel “Olhar real (heatmap)”. |
| **Camadas > predição IA** | U: mantém **Previsão da IA** marcado. S: exibe painel paralelo com filtro visual distinto. |
| **Camadas > sobreposição** | U: marca **Sobreposição comparativa**. S: combina visualmente as duas camadas para inspeção de *overlap*. |
| **Métricas > leitura** | U: lê a **metrics-bar** (antecipação, checagens, nota orientativa). S: apresenta números lado a lado usuário × modelo. |

---

## Relatórios

| Tópico > subtópico | U · S |
| :--- | :--- |
| **Escopo > motorista** | U: mantém opção “Eu — …” no seletor de usuário/sessão. S: restringe exportação ao titular autenticado. |
| **Escopo > administrador** | U: escolhe outro motorista na lista estendida (futuro) ou mantém visão global. S: habilita título “Relatórios (qualquer motorista)”. |
| **Período > datas** | U: ajusta **Data inicial** e **Data final**. S: valida ordem cronológica; se invertido, exibe erro de formulário. |
| **Formato > PDF** | U: clica em **Gerar PDF**. S: abre `relatorio-exemplo.html` em nova aba (protótipo) ou gera binário na integração. |
| **Formato > CSV** | U: clica em **Exportar CSV**. S: inicia download ou fila de geração; deve anexar dicionário de colunas em produção. |
| **Ajuda > legenda PDF/CSV** | U: lê o texto auxiliar sob as datas. S: explica diferença entre visualização estruturada e planilha/Power BI. |

---

## Administração e Sobre

| Tópico > subtópico | U · S |
| :--- | :--- |
| **KPIs > leitura rápida** | U: abre **Administração**. S: mostra cartões numéricos (vídeos enviados, taxa de sucesso fictícia, alertas). |
| **KPIs > consistência com Início** | U: compara números com a aba **Início** (admin). S: deve manter mesma fonte de dados agregada para evitar contradição. |
| **Sobre > limitação de responsabilidade** | U: lê o bloco institucional. S: posiciona linguagem de apoio à decisão, não substituição humana nem laudo legal automático. |

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
