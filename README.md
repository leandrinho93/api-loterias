🍀 Estratégia Loteria - API e Deep Linking
Este repositório atua como a infraestrutura de backend (servidor) estático e gratuito para o aplicativo Android Estratégia Loteria. Utilizando o poder do GitHub Pages, este projeto fornece os resultados atualizados das loterias e gerencia o sistema de redirecionamento inteligente (Deep Linking) para o compartilhamento de bolões entre os usuários.

📊 1. Como funciona a API de Resultados (Arquivos .json)
O aplicativo Android funciona com uma arquitetura Offline-First (desenhado para funcionar sem internet). No entanto, para atualizar os resultados dos sorteios e calcular os prêmios pendentes, o aplicativo faz requisições silenciosas para os arquivos .json hospedados na raiz deste repositório.

Possuímos um arquivo JSON dedicado para cada modalidade lotérica da Caixa Econômica Federal:

diadesorte.json

duplasena.json

lotofacil.json

lotomania.json

maismilionaria.json

megasena.json

quina.json

supersete.json

timemania.json

Estrutura de Dados (Exemplo)
Cada arquivo segue um padrão rigoroso de formatação para que o algoritmo do aplicativo consiga ler, processar e cruzar os acertos automaticamente. Exemplo do arquivo megasena.json:

JSON
{
  "concurso": 3008,
  "data": "14/05/2026",
  "dezenas": [ "11", "12", "14", "20", "42", "44" ],
  "acumulou": true,
  "trevos": [],
  "mesSorte": null,
  "premiacoes": [
    {
      "vencedores": 0,
      "premio": 60000000
    }
  ],
  "valorEstimadoProximoConcurso": 65000000,
  "dataProximoConcurso": "16/05/2026",
  "motivoPausa": null
}
Principais Campos:
concurso e data: Identificam o sorteio vigente.

dezenas (e dezenas2): Arrays contendo as dezenas sorteadas. No caso da Dupla Sena, o sistema lê um segundo array para o segundo sorteio.

Campos Específicos: Variáveis como trevos (+Milionária), mesSorte (Dia de Sorte) e timeCoracao (Timemania) são tratadas dinamicamente pelo motor estatístico do app.

acumulou e premiacoes: Ditam as mensagens de alerta visual no card principal do aplicativo (informando se há ganhadores ou se o prêmio acumulou).

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

📲 Baixe o Aplicativo
Organize seus bolões, utilize a sequência de Fibonacci e otimize suas apostas baixando o Estratégia Loteria direto na Google Play Store.

Desenvolvido por Leandro Silva da Costa.
