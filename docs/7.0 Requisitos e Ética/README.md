# Entrega 7: Requisitos e Ética

---

## 1) Que dados coletar?

### 1.1 Dados sobre o próprio usuário

- Faixa etária, contexto de uso (dirige com frequência? atua em frota/pesquisa/dev?)
- Formação (quando aplicável: área técnica, tempo de experiência no domínio)
- Hábito de leitura em tela e preferência de aprendizado (texto, vídeo, “aprendo usando”)

### 1.2 Dados sobre a relação com tecnologia

- Conforto com sites, apps, upload de vídeo, dashboards e PDF
- Experiência com câmera no veículo, telemetria, ferramentas de frota ou laboratório
- Hardware habitual (celular, notebook, resolução)
- Atitude em relação à **IA** analisando comportamento (confiança, medo, condições para confiar)

### 1.3 Dados sobre o conhecimento do domínio

- O que entende por **atenção visual** na direção
- Familiaridade com eye tracking, simuladores, ADAS
- Expectativa sobre saídas do sistema (heatmap, métricas, relatório, comparação com IA)

### 1.4 Dados sobre as tarefas

- Objetivos ao usar a plataforma (treino do modelo, predição, relatório, visão admin)
- Frequência esperada de cada tarefa; quais são **primárias** vs **secundárias**
- Gravidade percebida de erros (vídeo perdido, relatório confuso, interpretação errada da IA)

### 1.5 Dados sobre motivações e valores

- Privacidade dos vídeos e dos trajetos vs utilidade da análise
- Valorização de simplicidade vs métricas avançadas
- Disposição para investir tempo aprendendo o sistema
- Medo de julgamento (condutor) vs necessidade de evidência objetiva (frota/pesquisa)

---

## 2) De quem coletar?

Conforme Barbosa & Silva (2010): **usuários finais** e **stakeholders**.

| Perfil | Justificativa |
|--------|----------------|
| **Condutor de rua** (persona Gustavo) | Usuário primário do relatório individual e do upload |
| **Especialista em segurança veicular / frota** (Rogério) | Necessidade de métricas agregadas, exportação, comparabilidade |
| **Pesquisadora em veículos autônomos** (Bárbara) | Métricas detalhadas, dados brutos, documentação |
| **Engenheira de software / produto** (Poliana) | API, escalabilidade, logs, versionamento |
| **Orientador e definidores de escopo do TCC** | Alinhamento de objetivos e funcionalidades do sistema |

**Perguntas norteadoras:**

- Quem utilizará o sistema? → Condutores, pesquisadores, gestores de frota, devs ADAS  
- Quem será afetado? → Próprio condutor, empresa, participantes de pesquisa (anonimização)  
- Quem decide objetivos e funcionalidades? → Equipe do TCC + orientação acadêmica  
- Quem definiu os processos apoiados? → Modelagem do pipeline (vídeo → IA → dashboard/relatório)  

---

## 3) Aspectos éticos

Referência: **Resolução nº 196/96 do Conselho Nacional de Saúde** (orientação geral para pesquisa com pessoas; em projetos técnicos de IHC costuma-se seguir os mesmos princípios).

| Princípio | Aplicação no BVRAI |
|-----------|-------------------|
| **Não maleficência** | Não incentivar gravação **durante** a condução; deixar claro que o produto é para análise **pós-evento**; evitar uso de resultados para punição sem política explícita (frota) |
| **Justiça e equidade** | Participantes beneficiados por interface mais clara; não sobrecarregar grupos vulneráveis sem contrapartida |
| **Autonomia** | Consentimento livre e esclarecido; participação voluntária; direito de recusar/desistir; cuidado com menores e subordinados em pesquisas de frota |
| **Beneficência** | Uso dos dados para melhorar segurança e pesquisa; transparência sobre limites da IA |

**Na prática:**

- Explicar objetivos da pesquisa de necessidades **antes** do questionário  
- Garantir **confidencialidade** dos dados brutos e **anonimato** em divulgações públicas  
- Não solicitar dados desnecessários (ex.: identificação precisa de endereços ou placas)  
- **Termo de consentimento** ou texto de aceite no formulário, quando aplicável  

---

## 4) Ferramenta de coleta de dados

**Instrumento escolhido:** questionário online (**Google Forms**).

**Justificativa (Barbosa & Silva, 2010):** permite coletar dados de vários usuários de forma rápida, padronizada e assíncrona, adequada ao público (condutores, pesquisadores, profissionais com agenda restrita).

**Aplicação:** link compartilhado por WhatsApp/e-mail; introdução com objetivos e garantias éticas no próprio formulário; tempo estimado **8–12 minutos**.

**Roteiro completo do questionário (para copiar ao Forms):** [Questionário - BVRAI.md](./Questionário%20-%20BVRAI.md)