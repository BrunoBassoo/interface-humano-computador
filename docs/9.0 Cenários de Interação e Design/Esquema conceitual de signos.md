# Esquema conceitual de signos

Cada **signo** é um elemento da interface (ou do material apresentado) com **origem**, **tipo de conteúdo**, **restrições** de uso, **prevenção** de erro/mau uso e **recuperação** quando algo falha (Barbosa e Silva, 2010). A lista abaixo cobre o protótipo **`bvrai-interface`** de forma **exaustiva** — inclusive textos auxiliares, *badges*, *pills* e estados simulados; na integração com **API** e **MySQL**, a coluna *Origem* ganha também registros persistidos.

| Signo | Origem | Tipo de conteúdo | Restrição | Prevenção | Recuperação |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Ícone da marca (quadrado gradiente)** | Interface | Identidade visual | Não interativo | Contraste com fundo escuro | N/A |
| **Título “BVRAI — Behavioral Visual Replicating AI”** | Interface | Texto fixo | Leitura obrigatória para contexto | Subtítulo explica sigla | N/A |
| **Subtítulo monoespaçado (`JetBrains Mono`)** | Interface | Texto técnico curto | Pode ser ignorado por leigos | Mantém-se curto | N/A |
| **Badge “Protótipo IHC”** | Interface | Rótulo de versão | Indica não ser produção final | Cor secundária para não competir com ações | N/A |
| **Rótulo “Entrar na plataforma” (`aria-label`)** | Interface | Acessibilidade | Leitores de tela | Repete função do formulário | N/A |
| **Campo “Usuário” (`#login-user`)** | Interface + titular | Texto alfanumérico | Obrigatório (`required`) | *Placeholder* “usuario ou admin” | Foco retorna ao campo com mensagem de validação HTML5 |
| **Campo “Senha” (`#login-pass`)** | Interface + segredo | Senha mascarada | Obrigatório | *Placeholder* genérico; `autocomplete` adequado | Idem |
| **Botão implícito de envio do formulário de login** | Interface | Ação primária | Depende de rede na integração real | Estado *loading* a adicionar | Mensagem de timeout amigável |
| **Mensagem `#login-error`** | Interface | *Feedback* negativo | Oculta até primeira falha | `role="alert"` | Some após login bem-sucedido ou nova tentativa |
| **Bloco de ajuda com credenciais de demonstração** | Interface / projeto | Texto instrucional | **Não** repetir em produção com senhas reais | Aviso “apenas protótipo” implícito pelo *badge* | Remover ou substituir por “esqueci minha senha” |
| **Contêiner `#main-app`** | Interface | *Shell* da aplicação | Só visível após autenticação | Classe `hidden` até login | Volta a `hidden` ao sair |
| ***Pill* de usuário (`#user-pill`)** | Sistema (sessão) | Nome + papel | Atualiza conforme `role` | *Tag* “Admin” quando aplicável | Re-render ao trocar de conta |
| **Botão “Sair” (`#btn-sair`)** | Interface | Ação destrutiva de sessão | Encerra contexto imediato | Confirmação opcional em produção | Novo login |
| **Aba “Início” (`#tab-inicio`)** | Interface | Navegação principal | Sempre presente | `aria-selected` e `aria-controls` | Foco gerenciado ao trocar aba |
| **Aba “Vídeos”** | Interface | Navegação | Sempre presente | Idem | Idem |
| **Aba “Minha análise” (classe `tab-user-only`)** | Interface + política de papel | Navegação | **Oculta** para administrador | Remoção do nó ou `tab-hidden` | N/A para admin |
| **Aba “Relatórios”** | Interface | Navegação | Sempre presente | Idem | Idem |
| **Aba “Administração” (`tab-admin-only`)** | Interface + política de papel | Navegação | **Oculta** para motorista | `tab-hidden` até `role=admin` | Aparece após re-login admin |
| **Aba “Sobre”** | Interface | Navegação | Sempre presente | Idem | Idem |
| **Painel Início — saudação motorista (`#inicio-user`)** | Interface + dados de conta | Texto dinâmico | Depende de `displayName` | Nome padrão “motorista” se vazio | Fallback textual |
| **Cartões explicativos do Início (motorista)** | Interface | Texto + lista | Informacional | Duas colunas *card* | N/A |
| **Bloco estatístico do Início (motorista)** | Interface / *mock* | Números agregados fictícios | Não são dados reais em protótipo | Texto pequeno “mock” implícito pelo contexto acadêmico | Sincronizar com consulta SQL em produção |
| **Painel Início — visão admin (`#inicio-admin`)** | Interface + papel | Texto + estatísticas | Mutuamente exclusivo com `#inicio-user` | `tab-hidden` controlado por script | Exibir apenas um bloco por vez |
| **Opção *radio* “Vídeo para treinamento do modelo”** | Interface | Escolha exclusiva | Parte do grupo `name="tipo"` | Primeira opção marcada por padrão | Usuário pode voltar antes de confirmar envio |
| **Opção *radio* “Vídeo para predição”** | Interface | Escolha exclusiva | Exclusiva com treino | Texto explica diferença no mesmo *card* | Idem |
| **Zona de *upload* (“Arraste ou clique”)** | Interface | Área de *drop* | Ainda sem `input type=file` visível no protótipo | Botão “Escolher arquivo” como alternativa | Mensagem se *drag* não suportado |
| **Texto “Formatos sugeridos: MP4…”** | Interface | Ajuda contextual | Não vinculante legalmente sem T&C | Lista curta de formatos | Link para documentação de *codec* |
| **Botão “Escolher arquivo”** | Interface | Ação | Abre diálogo nativo do SO | Desabilitar se modo não selecionado (futuro) | Reabrir diálogo |
| **Botão “Confirmar envio”** | Interface | Ação | Pode ser clicado sem arquivo (risco) | Desabilitar até arquivo válido (melhoria) | Mensagem “Selecione um arquivo primeiro” |
| **Título “Meus envios”** | Interface | Texto estrutural | Motorista apenas | Hierarquia `h3` | N/A |
| **Lista `.status-list` (motorista)** | Interface + futuro *backend* | Sequência de pares arquivo/status | Ordenação por data a definir | *Pills* coloridas | Estado vazio com “Nenhum envio ainda” |
| **Nome de arquivo na lista (ex.: `sessão_…mp4`)** | Sistema / BD | *String* identificadora | Pode conter dados sensíveis no nome | Aviso para renomear antes do envio (política) | Renomeação local |
| **Selo “Concluído” (classe `pill ok`)** | Sistema / BD | Estado terminal | Cor verde semântica | Legenda de cores na documentação | Se regressar a erro, mostrar motivo |
| **Selo “Na fila” (`pill queue`)** | Sistema / BD | Estado intermediário | Ordem FIFO a garantir no servidor | Timestamp opcional | Cancelar *job* (futuro) |
| **Selo “Processando” (`pill run`)** | Sistema / BD | Estado ativo | Duração variável | Barra de progresso detalhada (melhoria) | *Timeout* com opção de reprocessar |
| **Título “Fila global de vídeos” (admin)** | Interface | Texto | Visível só em `#videos-admin` | *Lead* explica escopo | N/A |
| **Cartão informativo sobre *upload* por terceiros** | Interface | Texto legal/técnico | Protótipo sem ação | Evita promessa falsa de botão | Link para API quando existir |
| **Lista global com prefixo `usuário · arquivo`** | Interface / BD | Dados tabulares | Exposição de identificadores | Pseudonimização em produção | *Mask* em UI para não-admins |
| **Título “Dashboard de análise crítica individual”** | Interface | Texto | Só motorista | *Lead* com promessa comparativa | Redirecionar se sessão expirou |
| **Parágrafo *lead* de Minha análise** | Interface | Texto explicativo | Vocabulário “cruzamentos / faixa” | Glossário *tooltip* (melhoria) | N/A |
| **`<select>` “Sessão”** | Interface / BD | Lista de sessões | Deve refletir tabela de sessões | Primeira opção válida selecionada | Mensagem se lista vazia |
| **`<select>` “Período”** | Interface | Agregação temporal | Afeta métricas da barra inferior | Rótulo `aria-label` | Reset para “Última sessão” |
| **Checkbox “Mapa de atenção real”** | Interface | Booleano visual | Pode desligar camada | Marcado por padrão | religar para evitar tela vazia |
| **Checkbox “Previsão da IA”** | Interface | Booleano | Par com “real” | Idem | Idem |
| **Checkbox “Sobreposição comparativa”** | Interface | Booleano | Só faz sentido com ambas camadas | Desmarcar se uma camada off | Mensagem explicativa |
| **Painel *heatmap* “Olhar real”** | Modelo + captura | Mapa de cor | Dados simulados no HTML | Rótulo sobreposto no *mock* | *Fallback* imagem estática |
| **Painel *heatmap* “Predição IA”** | Modelo | Mapa de cor | Mesma geometria que o real | Filtro CSS distinto no protótipo | Sincronizar escala na integração |
| **Barra `.metrics-bar` (linhas de métricas)** | Sistema | Texto semi-numérico | **Nota orientativa** não é norma legal | Tipografia diferenciada para “B+” | *Tooltip* com definição da nota |
| **`#rel-titulo` (título de Relatórios)** | Interface + papel | Texto dinâmico | Muda com perfil admin | Atualização por script | Consistência com permissões |
| **`#rel-lead` (texto introdutório)** | Interface | Texto | Cita GOMS explicitamente | Mantém curto | N/A |
| **Seletor `#rel-user` (“Eu — …”)** | Interface / BD | Opções de escopo | Admin vê lista estendida (futuro) | Primeira opção “Eu — todas…” | Validar se sessão existe |
| **Campo data inicial `#d1`** | Interface | Data ISO | Não pode ser posterior à final | `type="date"` nativo | Mensagem de validação |
| **Campo data final `#d2`** | Interface | Data ISO | Par com `d1` | Idem | Idem |
| **Nota “PDF … CSV … Power BI”** | Interface | Ajuda | Informativo | Fonte menor, cor secundária | Link para dicionário de colunas |
| **Link “Gerar PDF” (`relatorio-exemplo.html`)** | Interface + arquivo estático | Ação abre nova aba | *Popup* pode ser bloqueado | `rel="noopener"` já presente | Instruir usuário a permitir *popup* |
| **Botão “Exportar CSV”** | Interface | Ação | Sem download no protótipo | Estado desabilitado ou *toast* “em breve” | Implementar *endpoint* |
| **Cartões KPI em Administração** | Interface / agregação BD | Números + rótulos | Dados fictícios | Alinhar com mesma fonte que Início admin | *Refresh* manual ou automático |
| **Tabela ou lista em Administração** | Interface / BD | Dados operacionais | Paginação futura | Cabeçalhos claros | *Empty state* |
| **Título “Sobre o projeto (TCC / IHC)”** | Interface | Texto institucional | Versão estática | Lista de funcionalidades | Atualizar a cada entrega |
| **Lista de funcionalidades na aba Sobre** | Interface | Marcadores | Pode ficar desatualizada | Revisão a cada *sprint* | Data da última atualização (opcional) |
| **`sessionStorage` (sessão cliente)** | Navegador | Par chave-valor | Volátil ao fechar aba | *Pill* de perfil indica sessão ativa | Re-login |
| **Script de alternância de abas / painéis** | Interface | Lógica de UI | Deve manter `hidden` e `aria-selected` coerentes | Testes de teclado | Reset ao detectar inconsistência |

---

## Signos de infraestrutura (além da tela)

Elementos que **não são widgets**, mas afetam a interpretação dos signos acima:

| Signo | Origem | Tipo de conteúdo | Restrição | Prevenção | Recuperação |
| :--- | :--- | :--- | :--- | :--- | :--- |
| **Registro de *job* de processamento** | MySQL (futuro) | Linha com `status`, `id`, `user_id` | Estados válidos enumerados | Máquina de estados no servidor | *Retry* idempotente |
| **Arquivo de vídeo em objeto de armazenamento** | *Object storage* / disco | Binário | Tamanho máximo | Validação no *upload* | Limpeza de *orphans* |
| **Relação FK usuário → envios** | MySQL | Integridade referencial | *ON DELETE* conforme política | Migrações versionadas | *Rollback* |
| **Log de auditoria de exportação** | MySQL / *ELK* | Evento | LGPD + necessidade de saber | Não logar conteúdo sensível desnecessário | Consulta por administrador |

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
