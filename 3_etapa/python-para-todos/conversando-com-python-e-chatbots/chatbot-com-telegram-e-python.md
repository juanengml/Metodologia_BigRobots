---
description: Vamos construir um bot simples usando a biblioteca telepot
---

# Bot com Telegram e Python

![](../../../.gitbook/assets/image%20%286%29.png)

### Acesse o BotFather 

{% embed url="https://telegram.me/BotFather" %}

Siga os tutoriais para conseguir o token do seu bot.

![](../../../.gitbook/assets/image%20%287%29.png)

### Instalando Biblioteca  utilizada

```bash
$ pip install telepot
```

Com a biblioteca instalada usamos nosso token da seguinte formar

```python
# -*- coding: utf-8 -*-

import time
import telepot
from telepot.loop import MessageLoop
import os

```

Criando variáveis do token e mensagem inicial

```python
std = """Oi, me chamo FinBot seu primeiro bot com telegram """
TOKEN = "TOKEN"
```

Função de handler para recebimento de mensagem e inicio de conversação

```python
def handle(msg):
    content_type, chat_type, chat_id = telepot.glance(msg)
    print(content_type, chat_type, chat_id)
    
    if content_type == 'text':
    	print msg['text']
    	if msg['text'] == "Oi":
          bot.sendMessage(chat_id, std)
```

Cria uma instanciar da nossa biblioteca com a variável e manda rodar a aplicação

```python
bot = telepot.Bot(TOKEN)
MessageLoop(bot, handle).run_as_thread()
print ('Listening ...')

# Keep the program running.

while 1:
        time.sleep(5)
```

Fim ! Rode Tudo é Seja feliz ! !! 

![](http://3.bp.blogspot.com/-mezFQuiBLdQ/T0-z3j5WfUI/AAAAAAAADrg/TllczQzSOB0/s1600/Hacker+goldfinger+3D+Animated+Gif+at+Hacker+Informer+Artful+3D+GIF+Animator+GIF+Animator+DDD+Ulead+GIF+Animator+websites+blogs+photo+graphics+clipart+the+attention+computer+program+free+download+.gif)



