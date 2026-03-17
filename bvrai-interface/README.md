# Interface BVRAI (protótipo HTML)

Protótipo de interface com **6 abas** para o projeto *Behavioral Visual Replicating AI* (IHC / TCC).

## Como abrir

Abra o arquivo `index.html` no navegador (duplo clique ou arrastar para Chrome/Edge/Firefox).

## Login (protótipo)

| Perfil    | Usuário  | Senha     | O que vê |
|-----------|----------|-----------|----------|
| Motorista | `usuario` | `123456` | Abas: Início, Vídeos, **Minha análise**, Relatórios, Sobre — sem Administração |
| Admin     | `admin`   | `admin123` | Abas: Início, Vídeos, Relatórios, **Administração**, Sobre — sem Minha análise; fila global de vídeos e relatórios por motorista |

Use **Sair** para trocar de conta. A sessão fica em `sessionStorage` (some ao fechar a aba).

## Abas

1. **Início** — contexto, público-alvo e estatísticas resumidas  
2. **Vídeos** — upload treino/predição e status (mock)  
3. **Minha análise** — dashboard individual real × IA  
4. **Relatórios** — exportação PDF/CSV  
5. **Administração** — métricas da plataforma  
6. **Sobre** — equipe e escopo do TCC  

OBS: É apenas **layout demonstrativo**.
