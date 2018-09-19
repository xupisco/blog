+++
author = "leandro"
title = "Flappybird Clone usando CoronaSDK"
date = 2017-06-26T12:28:31-03:00
description = ""
tags = ['corona', 'lua', 'tutorial']
draft = false
images = [
    "https://xupisco.net/img/og/flappy-bird-cover.jpg",
]
+++

Olás pessoas que não conheço, como estão?  
Vou começar uma série de tutoriais sobre como criar um clone de FlappyBird usando o [CoronaSDK](http://coronalabs.com), que é em Lua. 

**Update:** Já estão disponíveis os [2 primeiros posts](/flappybird-tutorial/)... comece agora!

![FlappyBird](../../static/img/flappy_bird-animated.gif)

Ainda estou preparando todo o material necessário, mas vamos começar do zero (mesmo) até ter o jogo completo rodando no seu celular. Por enquanto, já coloquei o source-code da versão final do projeto no github, fique a vontade se quiser baixar e começar a brincar antes.

Clone agora o **[Full flappy-bird source code](https://github.com/xupisco/CoronaSDK-FlappyBird)** em Lua.

**Tópicos abordados**  
Segue um "índice" sobre o que vamos passar / aprender neste tutorial:

 - Baixando e instalando o CoronaSDK
 - Criando o projeto
 - [Baixando os "assets" do jogo](https://github.com/xupisco/CoronaSDK-FlappyBird/raw/master/FlappyBird%20Assets.zip)
 - Configurando nosso game:
    - Resolução
    - Ícones
 - Entendendo o ```composer```
 - Criando nossas cenas (telas):
    - Principal
    - Game
    - GameOver
    - Highscore
 - Breve introdução a OOP em Lua
 - Criando nossos atores (objetos)
 - Colocando tudo junto (o game em si)
 - Considerações finais

Para os apressados, podem baixar o [CoronaSDK](https://developer.coronalabs.com/downloads/daily-builds#tabs-2) (tem que criar um cadastro) e começar a dar uma lida nos [guias](https://docs.coronalabs.com/guide/index.html) ou na [documentação](https://docs.coronalabs.com/api/index.html), além de rodar o jogo completo que pode ser baixado no github pelo link acima!

```lua
display.setDefault('magTextureFilter', 'nearest')
display.setDefault('minTextureFilter', 'nearest')

local composer = require('composer')

composer.recycleOnSceneChange = true
composer.effectList.fade.from.transition = easing.outQuad
composer.effectList.fade.to.transition = easing.outQuad

composer.gotoScene('scenes.menu')
```

Aguardem...  
[]'s