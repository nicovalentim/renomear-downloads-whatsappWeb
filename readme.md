# O que é?

Script simples que funciona como extensão do chrome para renomear arquivos com o Nome/Número de um contato de whatsapp web.

<img src="preview.gif" />

# Como instalar

1. baixe a versão zipada do repositório;
2. dentro do Chrome, abra [a aba de extensões](chrome://extensions);
3. entre no Modo de Desenvolvedor / Developer Mode;
4. Clique em carregar sem compatação / load unpacked, e escolha a pasta;
5. Recarregue o WhatsApp Web.

# Como funciona

Função | O que faz | Aonde encontrar
---|---|---
`extrairContato()` | Busca no header pelo nome/número do contato de whatsapp; | [`content.js`](content.js), linha 1
`existeDownload()` | Adiciona um ouvinte para caso algum botão de download é pressionado; | [`content.js`](content.js), linha 26
`runtime.onMessage` | Monitora o último contato selecionado; | [`background.js`](background.js), linha 2
Função Principal: `runtime.onDeterminingFilename` | Modifica o nome do arquivo para o nome do contato; | [`background.js`](background.js), linha 11
`limpaContato()` | Arruma nomes de contato com caracteres especiais, com diversos regex; | [`background.js`](background.js), linha 22
`criarNomeArquivo()` | Cria o nome do arquivo correto. | [`background.js`](background.js), linha 37
[`manifest.json`](manifest.json) | Informações para o Chrome, e limita o acesso à [`https://web.whatsapp.com/`](Web Whatsapp) | [`manifest.json`](manifest.json)
