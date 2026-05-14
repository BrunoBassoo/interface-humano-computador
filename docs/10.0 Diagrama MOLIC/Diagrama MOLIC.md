# Diagrama MOLIC

O **MOLIC** (*Model of Interaction as Conversation*) descreve a interação como troca de intenções entre usuário e sistema, incluindo rupturas e retomadas. Abaixo, versão condensada do fluxo principal de **envio de vídeo para predição** e leitura de resultado no BVRAI.

## Diagrama (visão conversacional)

```mermaid
flowchart TB
    subgraph U["Usuário (motorista)"]
        U1["Quero entender minha atenção neste trecho"]
        U2["Aceito enviar este arquivo agora"]
        U3["Preciso ver se o sistema entendeu o vídeo"]
        U4["Quero comparar meu olhar com a IA"]
    end

    subgraph S["Sistema BVRAI"]
        S1["Solicito modo: treino ou predição"]
        S2["Confirmo recebimento e posição na fila"]
        S3["Informo progresso ou erro de processamento"]
        S4["Apresento métricas e camadas comparativas"]
    end

    U1 --> S1
    S1 --> U2
    U2 --> S2
    S2 --> S3
    S3 -->|sucesso| S4
    S3 -->|falha| R1["Ruptura: mensagem de causa e próximo passo"]
    R1 --> U2
    U3 --> S3
    S4 --> U4
```

## Comentário estrutural

- **Abertura:** o sistema explicita o **modo** de uso para evitar expectativa incorreta sobre o que será feito com o vídeo.  
- **Meio:** a conversa permanece no registro de **estado** até que o processamento assíncrono conclua; silêncio prolongado é tratado como risco de ruptura.  
- **Encerramento:** a camada comparativa fecha o ciclo com resposta à intenção inicial de “entender atenção”.

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
