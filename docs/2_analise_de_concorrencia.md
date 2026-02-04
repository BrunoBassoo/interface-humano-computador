# Análise de Concorrência  

## Identificação dos Principais Concorrentes

### 1. Smart Eye – Driver Monitoring System

- **Link:** https://www.smarteye.se/solutions/automotive/driver-monitoring-system/
- **Descrição:**  
  Sistema avançado de monitoramento do motorista utilizando IA, visão computacional e eye tracking. Detecta distração, fadiga, sonolência e comportamento de risco. Amplamente adotado por montadoras globais.

- **Imagens de Interface (para coleta):**  
  - Dashboards de atenção do motorista  
  - Alertas visuais de distração/fadiga  
  - Visualização de posição da cabeça e olhar  

---

### 2. Tobii – Driver Monitoring System (DMS)

- **Link:** https://www.tobii.com/products/automotive/tobii-dms
- **Descrição:**  
  Plataforma robusta de eye tracking automotivo focada em segurança veicular e conformidade regulatória. Atua em tempo real mesmo em condições adversas de iluminação.

- **Imagens de Interface (para coleta):**  
  - Telas de monitoramento em tempo real  
  - Indicadores de atenção do motorista  
  - Relatórios de eventos críticos  

---

### 3. Eyeware – GazeSense Driver Monitoring

- **Link:** https://www.eyeware.tech/driver-monitoring/
- **Descrição:**  
  SDK de rastreamento ocular 3D utilizado para desenvolvimento e prototipagem de sistemas DMS. Fornece dados de olhar, pose de cabeça e APIs para integração personalizada.

- **Imagens de Interface (para coleta):**  
  - Painel de visualização de gaze  
  - Ferramentas de calibração  
  - Gráficos de dados de atenção  

---

### 4. Neonode – Driver Monitoring Software

- **Link:** https://neonode.com/solutions/driver-monitoring
- **Descrição:**  
  Solução de monitoramento de motorista baseada em IA, focada em conformidade com normas como Euro NCAP e EU GSR. Detecta distração, fadiga e comportamento inseguro.

- **Imagens de Interface (para coleta):**  
  - Telas de status do motorista  
  - Alertas visuais embarcados  
  - Indicadores de risco  

---

## Características e Funcionalidades

| Concorrente | Eye Tracking | Detecção de Fadiga | Detecção de Distração | Alertas em Tempo Real | Relatórios |
|------------|-------------|--------------------|-----------------------|----------------------|------------|
| Smart Eye DMS | ✔️ | ✔️ | ✔️ | ✔️ | ✔️ |
| Tobii DMS | ✔️ | ✔️ | ✔️ | ✔️ | ✔️ |
| Eyeware GazeSense | ✔️ | ✔️ | ✔️ | ❌* | ❌* |
| Neonode DMS | ✔️ | ✔️ | ✔️ | ✔️ | ✔️ |

\* Depende da implementação feita pelo integrador.

---

## Experiência do Usuário (UX)

### Pontos Positivos

- Interfaces focadas em **visualização rápida de estados críticos**
- Uso consistente de **cores, ícones e alertas**
- Dashboards que traduzem dados complexos em métricas simples
- Feedback em tempo real aumenta a percepção de segurança

### Pontos Negativos

- Muitas soluções não possuem interface final pronta (foco em SDK)
- UX frequentemente voltada a engenheiros, não a usuários finais
- Curva de aprendizado elevada em ferramentas muito técnicas

---

## Preços e Modelos de Negócio

| Plataforma | Modelo de Negócio | Preço |
|-----------|------------------|--------|
| Smart Eye DMS | Licenciamento OEM / por volume | Sob consulta |
| Tobii DMS | Licença industrial automotiva | Sob consulta |
| Eyeware GazeSense | Licença de SDK | Sob consulta |
| Neonode DMS | Licença por projeto | Sob consulta |

> Observação: preços não são públicos e variam conforme volume, integração e escopo do projeto.

---

## Padrões e Tendências do Mercado

- Forte foco em **segurança veicular e regulamentações**
- Uso intensivo de **IA e visão computacional**
- Interfaces minimalistas e orientadas a alertas
- Crescente demanda por **dados explicáveis e visualizações claras**
- Integração com sistemas ADAS e veículos semi-autônomos

---

## Sumarização dos Resultados

A análise mostra que os principais concorrentes:
- Atuam majoritariamente como **plataformas técnicas ou SDKs**
- Priorizam robustez e precisão em detrimento de UX final
- Utilizam padrões visuais similares para alertas e status
- Oferecem oportunidades claras para inovação em interface e usabilidade

---

## Pontos Positivos e Negativos

### Pontos Positivos

- Alta confiabilidade técnica
- Métricas bem definidas de atenção e fadiga
- Interfaces consistentes para alertas críticos

### Pontos Negativos

- Falta de foco em UX para usuários finais
- Pouca transparência visual do funcionamento do sistema
- Interfaces muitas vezes pouco flexíveis

---

## Recomendações para o Software em Desenvolvimento

- Criar um **dashboard central de atenção do motorista**
- Utilizar **feedback visual e sonoro claro**
- Oferecer **configuração de sensibilidade e alertas**
- Priorizar **visualizações simples e intuitivas**
- Facilitar exportação de relatórios e dados
- Pensar na interface tanto para **tempo real quanto análise posterior**

---

