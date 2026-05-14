# Cenário de interação — Monitoramento administrativo

Rogério encerra uma reunião com o jurídico da empresa às 18h40. O combinado é simples: na manhã seguinte a diretoria quer um **número único** sobre quantos vídeos falharam no processamento na última semana e um exemplo de **código de erro** para acionar o fornecedor de *software*. Em casa, após o jantar, ele abre o notebook, entra no BVRAI com perfil **administrador** e vai direto à aba **Vídeos**, onde a interface já apresenta a **fila global**: cada linha mostra o usuário de origem, o nome do arquivo e um selo de status (Concluído, Processando, Na fila).

Ele rola a lista e identifica dois envios com estado anômalo: um permaneceu muito tempo em “Processando” sem atualização e outro voltou a “Na fila” após uma falha transitória. Rogério anota os identificadores exibidos ao lado do nome do arquivo — o protótipo sugere que, na versão integrada ao **MySQL**, esse identificador corresponderá à chave primária do *job* para cruzamento com logs do servidor. Em seguida ele abre **Administração** e confere os cartões de KPI: vídeos enviados, taxa de conclusão e alertas resumidos. A leitura é rápida porque os números estão no topo; os detalhes ficam na lista que ele já havia visto.

Para fechar o pacote para a reunião das 9h, Rogério acessa **Relatórios**, altera o título contextual para a visão “qualquer motorista”, escolhe o intervalo de datas da semana e exporta **CSV**, sabendo que a planilha alimentará o **Power BI** que o time de operações mantém. Antes de encerrar, ele clica em **Sobre** apenas para confirmar se a versão do protótipo e o escopo do TCC continuam alinhados ao que ele vai apresentar como “ferramenta de apoio”, e não como laudo automático de conduta. Satisfazido, faz **Sair** e arquiva os arquivos na pasta compartilhada da frota.

---

*Referência: BARBOSA, S. D. J.; SILVA, B. S. **Interação Humano-Computador**. Elsevier, 2010.*
