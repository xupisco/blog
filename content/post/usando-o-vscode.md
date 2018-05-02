+++
author = "leandro"
title = "Usando o VS Code com Hugo"
date = 2017-06-23T13:49:27-03:00
description = "Dicas para aproveitar melhor o VS Code no seu Blog com Hugo."
tags = ['tips']
draft = false
images = [
    "https://code.visualstudio.com/images/whyvscode_macwinlinux2.png",
]
+++

O [Hugo](https://gohugo.io/) é um excelente gerador de sites estáticos escrito em [Go](https://golang.org/), com uma documentação bem completa e vários [temas](https://themes.gohugo.io/) disponíveis (este blog utiliza o tema "**cocoa**", com alguma customização feita por mim).

Não quero entrar muito em detalhes sobre como instalar e configurar o Hugo, isso pode ser encontrado no ["Getting started"](https://gohugo.io/overview/introduction/) do site deles, o objetivo aqui é apenas falar sobre como deixar o VS Code mais esperto para ele.

![VS Code](https://code.visualstudio.com/images/whyvscode_macwinlinux2.png)
*VS Code é multi-plataforma, baixe agora*

### Como é o processo?

O Hugo funciona com um binário, disponível para todas as plataformas. É com ele que vc inicia seu blog, posts e compila os arquivos para .html. Basicamente, o workflow é o seguinte:

```bash
$hugo new site meu_novo_blog
$hugo new post/meu-primeiro-post.md # sim, usamos markdown \o/
$hugo serve --buildDrafts # inicia o servidor local
```

Pronto, só acessar ```http://localhost:1313``` para ver o seu novo blog. Sweet!

Uma grande vantagem de usar sites estáticos é poder hospedá-lo em qualquer lugar. Este que vc está lendo agora fica no [github](https://github.com), na faixa.

### Melhorando o VS Code

Até que enfim, bom, dois plugin que uso para editar e gerenciar este blog pelo VS Code, são eles:

 - [Markdown All in One](https://marketplace.visualstudio.com/items?itemName=yzhang.markdown-all-in-one)
 - [Hugofy](https://marketplace.visualstudio.com/items?itemName=akmittal.hugofy)

Vamos explicá-los:

**Markdown All in One**  
Esse cara facilita sua edição e visualização de arquivos markdown (com extenção .md) com as seguintes funcionalidades:

 - Melhor Syntax Highlight (corzinhas)
 - Live preview (side-by-side)
 - Atalhos para **negrito**, links, imagens, etc...

Ele até faz mais coisa, mas é isso que eu uso.

**Hugofy:**  
Este possui alguns atalhos para comandos do CLI (command line) do Hugo, para iniciar, basta digitar ```shift + ctrl + p``` no VS Code e digitar "hugo", alguns deles são:

 - Start server
 - Stop server
 - New site
 - New post

Bom, é isso... se precisar de alguma ajuda pra deixar sei site com Hugo "em pé", comenta ae que tento te ajudar!

[]'s