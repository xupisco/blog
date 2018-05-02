+++
author = "leandro"
title = "02 - Entendendo a estrutura do projeto"
date = 2017-06-27T10:32:20-03:00
description = "Tutorial FlappyBird - Entendendo a estrutura do projeto"
tags = ['tutorial', 'corona']
draft = false
images = [
    "http://isotopedia.com/img/og/flappy-bird-cover.jpg",
]
+++

Hello again... agora que você já [instalou o CoronaSDK e baixou o esqueleto do projeto]({{< relref "flappybird-tutorial/01_hello-world.md" >}}), podemos começar a colocar a mão na massa e dar vida ao nosso game (clone). Por enquanto temos apenas uma tela preta, parece ruim, mas já está funcionando e com todas as configurações necessárias para continuarmos o desenvolvimento.

Antes de baixar os assets e colocar nosso background, vou explicar como o CoronaSDK funciona e quais configurações estão nos arquivos iniciais.

## Rodando o game ##
Quando o Simulador inicia o projeto ele "lê", na sequência, os seguintes arquivos fundamentais para qualquer projeto em Corona:

1. config.lua
2. main.lua

> Se vc for esperto, vai perceber que na nossa raiz também existe um arquivo "build.settings", ele contém instruções sobre como compilar o projeto para determinado OS, irrelevante por enquanto.

Vamos começar com o **config.lua**:

```lua
application = {
	content = {
		width = 144,
		height = 256,
		scale = "zoomEven",
		fps = 60
	},
}
```

Esse bloco diz para o engine como é nosso aplicativo (ou game), passando as instruções explicadas abaixo:

 - **width**: Largura
 - **height**: Altura
 - **scale**: Como redimensionar nosso game *
 - **fps**: Frames Por Segundo

>\* Hoje em dia existem diversos tamanhos e formatos de telas nos devices (celulares), por isso temos que nos preocupar em como o game vai se comportar em cada um deles. Mais detalhes no decorrer deste tutorial... para os apressados, as opções são: "letterbox", "zoomEven", "adaptive" e "zoomStretch". Leia sobre elas [aqui](https://docs.coronalabs.com/guide/basics/configSettings/#scale).

Se você trabalha ou já trabalhou com desenvolvimento web, vai perceber que o arquivo "config.lua" parece um **json**, mas na verdade é uma [tabela](https://www.lua.org/pil/2.5.html) (em Lua), vale a pena entender melhor como elas funcionam, clique no link para ler mais.

---

Agora o **main.lua**:

> Esse é o principal cara do seu game, tudo começa aqui, por isso é importante entender como utilizá-lo de maneira eficiente. Nosso esqueleto está bem simples, vamos lá.

```lua
-- No antialias (pixelart games)
display.setDefault('magTextureFilter', 'nearest')
display.setDefault('minTextureFilter', 'nearest')

local composer = require('composer')

composer.recycleOnSceneChange = true
composer.effectList.fade.from.transition = easing.outQuad
composer.effectList.fade.to.transition = easing.outQuad
-- composer.gotoScene('scenes.menu')
```

**#tip:** Se ainda não percebeu, é com ```--``` que criamos comentários em Lua.

Agora calma, vamos por partes:  

```lua
-- No antialias (pixelart games)
display.setDefault('magTextureFilter', 'nearest')
display.setDefault('minTextureFilter', 'nearest')
```
Essas duas primeiras linhas, dizemos ao compilador como ele deve redimensionar nossas imagens, como nosso game é em "pixel-art", a melhor opção é "nearest", vai por mim. Na sequência...

```lua
local composer = require('composer')

composer.recycleOnSceneChange = true
composer.effectList.fade.from.transition = easing.outQuad
composer.effectList.fade.to.transition = easing.outQuad
```

O **composer** é responsável por cuidar das nossas "cenas". Todo game possui pelo menos uma. Mas o que é diabos é uma cena? Você pergunta, explico: É o que está na tela... WHAT?

Relax, olha só como é fácil... assim vc vai entender melhor.  
Algumas cenas "comuns" são:

 - Menu
 - Configurações
 - Fases:
    - Tutorial
    - Fase 01 .... N
 - Game Over
 - Placar

Sacou? Conforme a gente for criando o game (e as cenas) tudo fica mais claro... não se preocupe. Vamo-que-vamo, vai ficar legal!

## Baixando os Assets ##

Antes de tudo, um ponto **muito importante** aqui. NÃO use imagens em seus jogos sem que tenha o direito, de preferência por escrito, de quem as criou. Pirataria é crime e uso ilegal de imagens também, existe um tal de "[Direito Autoral](https://pt.wikipedia.org/wiki/Direito_autoral)" que deve ser respeitado.

As imagens e sons do **FlappyBird** são de propriedade do **Dong Nguyen**, como este tutorial é puramente educacional e sem fins lucrativos, vamos utilizá-las. Pronto, agora... [baixe aqui os assets do Flappy Bird] (https://github.com/xupisco/CoronaSDK-FlappyBird/raw/master/FlappyBird%20Assets.zip) e coloque no diretório "assets" do seu projeto, ficando:

| **Pasta**         | **Tipo de arquivo**    |
| :---------------- |:---------------------- |
| ./assets/SFX      | Efeitos sonoros (.mp3) |
| ./assets/sprites  | Imagens                |

Pronto, tudo no lugar... vamos fazer algumas coisa aparecer logo na tela antes que vc desista de continuar.

## Incluindo nosso background ##

Dentro da pasta "scenes" já deixei um arquivo chamado "**\_template.lua**", ele servirá como base para todas as nossas cenas. Para começar, faça uma cópia do "\_template.lua" e renomeie para "**game.lua**" (ainda dentro de scenes).

Dentro do arquivo que está na raiz "main.lua", remova o comentário da linha "--composer.gotoScene('scenes.menu')" e altere o que está dentro do parenteses para 'scenes.game', ficando:

```lua
composer.gotoScene('scenes.game')
```

Se ainda está com o Simulador aberto, ele deve atualizar sozinho... se não, abra o simulador o projeto, a tela ainda está preta. Vamos atualizar agora o arquivo "scenes/game.lua". Abra-o.

Vamos alterar a função "scene:create(event)" deixando dessa maneira:

```lua
-- create()
function scene:create(event)
    local group = self.view
	local background = display.newImageRect("assets/sprites/background_day.png", 144, 256)
	background.anchorX, background.anchorY = 0, 0
    background.x, background.y = 0, 0
	group:insert(background)
end
```

Apareceu uma imagem no simulador? Boa... vou explicar o que as novas linhas fazem, uma por uma.

```lua
local background = display.newImageRect("assets/sprites/background_day.png", 144, 256)
```
Aqui criamos uma variável "local" (dentro do escopo) do tipo "display.newImageRect", que é como o Corona exibe sprites na tela. Os parâmetros são:

1. Caminho do arquivo
2. Largura da imagem
3. Altura da imagem

```lua
background.anchorX, background.anchorY = 0, 0
background.x, background.y = 0, 0
```

Agora, mudamos o "pivot" da imagem para 0, 0... ou seja, no topo superior esquerdo e posicionamos a imagem na tela, também em 0, 0. Mais pra frente vc vai entender o que isso faz, vem comigo.

```lua
group:insert(background)
```

Para finalizar, incluímos nosso background no grupo "group". Todos os objetos do tipo "display" devem estar dentro deste grupo para que o composer saiba como tratar os elementos quando mudarmos de cena. Complicado? Nem é... vc chega lá!

---

É isso ai, agora já temos alguma coisa rodando e nosso game "começa" a existir. No próximo post vamos incluir o chão animado (dando ilusão de estar passando), além do pássaro e suas animações básicas!

See you there...  
Hugs!


