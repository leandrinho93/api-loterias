🔗 2. Sistema de Importação e Rede Viral (Pasta /importar)
O grande diferencial deste ecossistema é a pasta /importar. Ela contém um arquivo index.html que atua como a ponte para o sistema de Android App Links (Deep Linking).

O Estratégia Loteria permite que um usuário gere um "Bolão", divida as cotas e compartilhe os jogos gerados com seus amigos via WhatsApp. O link gerado possui o seguinte formato:
👉 https://leandrinho93.github.io/api-loterias/importar?codigo=LMTR-XYZ123...

O Fluxo Inteligente:
O que acontece quando o amigo clica no link no WhatsApp?

Se o aplicativo ESTIVER instalado: O sistema Android reconhece a assinatura de segurança, intercepta o clique e abre o aplicativo instantaneamente. O código criptografado (LMTR-XYZ...) é lido pelo app, que importa o bolão, salva os jogos no celular do amigo e passa a vigiar os resultados automaticamente.

Se o aplicativo NÃO ESTIVER instalado:
O Android não encontra o app e abre o navegador (Chrome). O navegador entra nesta pasta /importar do repositório. O arquivo index.html entra em ação e atua como um Fallback (Plano B), redirecionando o usuário instantaneamente para a página de download do Estratégia Loteria na Google Play Store.

Essa arquitetura cria um ciclo de crescimento orgânico (Growth Hacking), onde o próprio compartilhamento dos usuários atrai novos downloads de forma gratuita e fluida.

🛠️ Tecnologias e Arquitetura
Hospedagem: GitHub Pages (Serverless / Custo Zero)

Formato de Dados: JSON (JavaScript Object Notation)

Deep Linking: Intent URLs / Smart Fallback para Android

Aplicativo Cliente: Android (Kotlin) / WebView / JavaScript

📲 Baixe o Aplicativo.

Desenvolvido por Leandro Silva da Costa.
