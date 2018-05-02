+++
title = "Python - Remover valores duplicados de uma lista mantendo a ordem"
date = 2017-06-23T11:48:24-03:00
description = ""
tags = ['python', 'tips']
categories = []
draft = false
+++

No python, vc pode usar o ```set()``` para remover valores duplicados de uma lista, mas ele troca a ordem dos valores dentro dela, para mantê-los, é simples, veja o exemplo abaixo:

```python
lista = ['a', 'a', 'b', 'd', 'a', 'b', 'a', 'c', 'd']
sorted(set(lista), key=lambda x: lista.index(x)) #magic

#output
> ['a', 'b', 'd', 'c']
```

Simples assim...  
[]'s
