+++
author = "leandro"
title = "01 - Hello World"
date = 2017-06-27T10:17:56-03:00
description = "Criando um clone de FlappyBird no CoronaSDK"
tags = ['tutorial', 'corona']
draft = false
images = [
    "http://isotopedia.com/img/og/flappy-bird-cover.jpg",
]
+++

Olás pessoas, prontos para começarem no mundo da programação e desenvolvimento de jogos? Ainda não? Então pode ir assistir qualquer porcaria no [Youtube](http://www.youtube.com).

Vou dividir este tutorial em algumas partes, tentando ser o mais didático possível, além de explicar o porque dos caminhos escolhidos foi seguido. A ideia não é você "copiar" o código, mas sim entender como tudo foi feito, só assim poderá usar este aprendizado nos seus próprios projetos.

Mas eu só quero o código! Blz, pode baixar [aqui](https://github.com/xupisco/CoronaSDK-FlappyBird)... tchau!

## Pronto? Hello World ##

Vamos usar o engine **[CoronaSDK](http://coronalabs.com)** neste game. Ele é grátis, com uma documentação bem escrita e estruturada. Nele usamos a linguagem **Lua**, que é fácil de aprender e gostosa de programar. Perfeita para iniciantes.

```lua
print("Hello World")
```

Algumas outras vantagens do **CoronaSDK**:

 - É gratuito*
 - É em Lua (já expliquei)
 - Ótima [documentação](https://coronalabs.com/learn/)
 - Muitos plugins ([marketplace](https://marketplace.coronalabs.com/))
 - Multi-plataforma
 - Live Reload
 - Etc...

Conheça [todos os recursos](https://coronalabs.com/product/) no site deles.

**01: Baixando e instalando o CoronaSDK**  
Sem muita enrolação, siga os passos abaixo:

1. Faça [seu cadastro](https://developer.coronalabs.com/user/login) no site da Corona Labs
2. Faça o login
3. Baixe o [CoronaSDK](https://developer.coronalabs.com/downloads/coronasdk) para a sua plataforma
4. Instale (padrão wizard, ok, next, next, etc...)

Pronto, o SDK e o Simulador estão instalados, bora para a parte mais legal agora.

**02: Criando o projeto**  
Tem duas maneiras de começar, mas como sou bonzinho, já montei um esqueleto que vai além de agilizar setup do projeto, irá também ajudar na sua organização.

> Nada impede vc de abrir o simulador e selecionar "New Project", abaixo vou explicar porque usar este esqueleto.

Clone ou baixe o esqueleto do projeto no Github, [clicando aqui](https://github.com/xupisco/CoronaSDK-LowresGameTemplate) em uma pasta nova.

> Obs: Como uso windows, alguns atalhos ou outras coisas que encontrar aqui podem ser diferentes do OS que vc usa, mas no geral as coisas funcionam iguais.

Feito isso, vc terá uma pasta nova com a seguinte estrutura: (comando: ```$tree```)

```
Project_Template:
├── assets
│      ├── music
│      ├── sfx
│      └── sprites
├── classes
├── LaunchScreen.storyboardc
├── scenes
└── _icons
```

No Simulador, clique em "Open Project" e selecione o arquivo ```main.lua```, na raiz. Se tudo der certo (até agora não tem como estar errado) vai abrir uma janela com o fundo preto, na proporção de um celular.

Pronto, esse é o nosso jogo... rá!

Brincadeira, no [próximo post]({{< relref "flappybird-tutorial/02_understanding-the-skeleton.md" >}}) vou explicar pra que as pastas e os arquivos desse esqueleto servem. Vamos baixar os assets (arquivos) do jogo e fazer o background aparecer na tela.

Até!
