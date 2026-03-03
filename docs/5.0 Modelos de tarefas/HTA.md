1️⃣ Dashboard de Análise Crítica Individual

🎯 Objetivo

Permitir que o usuário visualize e compare seu comportamento real com a predição da IA.

```mermaid
graph TD

A["0. Visualizar análise crítica individual
1>2>3"]

A --> B["1. Selecionar período ou sessão
1/2"]

A --> C["2. Visualizar métricas
1+2"]

A --> D["3. Comparar comportamento real vs IA
1>2"]

B --> B1["1.1 Escolher sessão específica"]
B --> B2["1.2 Escolher intervalo de datas"]

C --> C1["2.1 Visualizar métricas do usuário"]
C --> C2["2.2 Visualizar métricas da IA"]

D --> D1["3.1 Exibir mapa de atenção real"]
D --> D2["3.2 Exibir previsão da IA"]
```

--------

2️⃣ Dashboard do Administrador

🎯 Objetivo

Monitorar o andamento e utilização da plataforma.

```mermaid
graph TD

A["0. Monitorar andamento da plataforma
1>2>3"]

A --> B["1. Visualizar métricas gerais
1+2+3"]

A --> C["2. Acompanhar utilização
1>2"]

A --> D["3. Identificar problemas
1/2"]

B --> B1["1.1 Número de usuários ativos"]
B --> B2["1.2 Volume de vídeos enviados"]
B --> B3["1.3 Status dos treinamentos"]

C --> C1["2.1 Ver acessos recentes"]
C --> C2["2.2 Ver taxa de uso por usuário"]

D --> D1["3.1 Detectar falhas no processamento"]
D --> D2["3.2 Detectar baixa adesão"]
```
------

3️⃣ Extração de Relatório Individual

🎯 Objetivo

Gerar relatório de desempenho do usuário.

```mermaid
graph TD

A["0. Gerar relatório individual
1>2>3>4"]

A --> B["1. Selecionar usuário"]
A --> C["2. Selecionar período"]
A --> D["3. Escolher formato
1/2"]
A --> E["4. Exportar relatório"]

D --> D1["3.1 PDF"]
D --> D2["3.2 CSV"]
```

----------

4️⃣ Envio de Vídeo para Treinamento ou Predição

🎯 Objetivo

Enviar vídeo para processamento na plataforma.

```mermaid
graph TD

A["0. Enviar vídeo para processamento
1>2>3>4"]

A --> B["1. Selecionar tipo de envio
1/2"]
A --> C["2. Fazer upload do vídeo"]
A --> D["3. Confirmar envio"]
A --> E["4. Acompanhar status"]

B --> B1["1.1 Vídeo para treinamento"]
B --> B2["1.2 Vídeo para predição"]
```
