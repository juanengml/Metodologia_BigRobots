---
description: >-
  #BotaAlmanoBot vamos usar um biblioteca chamada chatterbot para criarmos um
  bot para trocar umas ideias.
---

# Conversando com Python e Chatbots

Oi, vamos estudar juntos como criar um modelo de conversação para o chatbot poder interagir conosco.

### Mas, O que é Chatbot ? 

Chatbot é um programa de computador que tenta simular um ser humano na conversação com as pessoas. O objetivo é responder as perguntas de tal forma que as pessoas tenham a impressão de estar conversando com outra pessoa e não com um programa de computador.

![](https://miro.medium.com/max/480/1*NLbr0TzqDz98QhMUYyX41A.gif)

### Toda Frase em primeiro momento ele é dividida em partes. 

![](https://miro.medium.com/max/500/1*G7T4sFO-1ByMepsa5OilsQ.gif)

Em seguida temos essas partes convertida em números e passada por uma serie de processos que permitem extrair informações e aplicar em contextos de acordo com as entradas.

![](https://miro.medium.com/max/500/1*d_POV7c8fzHbKuTgJzCxtA.gif)

### OK, muito técnico neh ? 

#### Vamos para nosso tutorial que você vai entender melhor....

## Então ? Antes de Tudo...baixe a biblioteca...

Use o comando pip para fazer isso

```bash
pip install git+git://github.com/gunthercox/ChatterBot.git@master
```

Vale lembrar que ele vem sem nada de conversação, então toda vez que o usuario entra com um dado ele guarda como afirmação e quando algo semelhante e conferido retorna como saída.

```python
# importamos as bibliotecas de treino e chatbot
from chatterbot.trainers import ListTrainer
from chatterbot import ChatBot
```

Criamos nossa instancia de conversa como o nome do nosso bot

```python
bot = ChatBot('ChatBot')
```

Em seguida vamos definir nosso base de dados para conversas

```python
conversa = ['Oi', 'Olá', 'Tudo bem?',
           'Tudo ótimo', 'Você gosta de Biscoito?', 
           'Sim, eu gosto de bolacha']
```

Aqui vamos definir os o treino como ListTrainer e mandar treinar.

```python
bot.set_trainer(ListTrainer)
bot.train(conversa)
```

Em seguida vamos iniciar inicar os tests com nosso bot treinado.

```python

while True:
    pergunta = input("Me: ")
    resposta = bot.get_response(pergunta)
    if float(resposta.confidence) > 0.5:
        print('ChatBot: ', resposta)
    else:
        print('ChatBot: Ainda não sei responder esta pergunta')
```

Na linha  5 definimos o nivel de resposta para caso nivel de resposta seja compreensivel maior que 0.5 o bot responder de fato, caso contrario ele responde que não entendeu.

## Full Code

```python
from chatterbot.trainers import ListTrainer
from chatterbot import ChatBot

bot = ChatBot('ChatBot')

conversa = ['Oi', 'Olá', 'Tudo bem?',
           'Tudo ótimo', 'Você gosta de Biscoito?', 
           'Sim, eu gosto de bolacha']

bot.set_trainer(ListTrainer)
bot.train(conversa)

while True:
    pergunta = input("Me: ")
    resposta = bot.get_response(pergunta)
    if float(resposta.confidence) > 0.5:
        print('ChatBot: ', resposta)
    else:
        print('ChatBot: Ainda não sei responder esta pergunta')
```

### Viu como é Simples ? Então, treine seu bot usando essa suas proprias base de dados e veja o que acontece....{^\_^}



