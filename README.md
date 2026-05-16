# 🍀 Estratégia Loteria - API e Deep Linking

Este repositório atua como a infraestrutura de backend (servidor) estático e gratuito para o aplicativo Android **Estratégia Loteria**. Utilizando o poder do **GitHub Pages**, este projeto fornece os resultados atualizados das loterias e gerencia o sistema de redirecionamento inteligente (Deep Linking) para o compartilhamento de bolões entre os usuários.

---

## 📊 1. Como funciona a API de Resultados (Arquivos `.json`)

O aplicativo Android funciona com uma arquitetura *Offline-First* (desenhado para funcionar sem internet). No entanto, para atualizar os resultados dos sorteios e calcular os prêmios pendentes, o aplicativo faz requisições silenciosas para os arquivos `.json` hospedados na raiz deste repositório.

Possuímos um arquivo JSON dedicado para cada modalidade lotérica da Caixa Econômica Federal:
* `diadesorte.json`
* `duplasena.json`
* `lotofacil.json`
* `lotomania.json`
* `maismilionaria.json`
* `megasena.json`
* `quina.json`
* `supersete.json`
* `timemania.json`

### Estrutura de Dados (Exemplo)
Cada arquivo segue um padrão rigoroso de formatação para que o algoritmo do aplicativo consiga ler, processar e cruzar os acertos automaticamente. Exemplo do arquivo `megasena.json`:

```json
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
