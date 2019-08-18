# Python com Internet das Coisas

Nesse tutorial vamos trabalhar com o protocolo MQTT, vamos enviar e receber uma mensagem e entender como ele se comporta em uma rede local.

### Arquitetura da Nossa rede Local

![](https://www.hivemq.com/img/blog/shared-subscriptions.gif)

Nos vamos escrevermos os publishers e o broker vai repassar a mensagem para os outros dispostivos da rede.

### Arquitetura de Rede Externa

![](https://files.readme.io/2851ca2-giphy_1.gif)

Observe que nesse ambiente a informação vai para fora da rede e passa por um servidor broker que retransmite a mensagem.

### Como fazer tudo isso com python ? 

Em seu linux instale por linha de comando usando pip

```bash
$ pip install paho-mqtt
$ sudo apt install mosquitto mosquitto-clients
```

Depois que instalamos nossa biblioteca em nosso computador vamos instalar ela em nosso raspiberry é nele que vamos nos comunicarmos o comando é exatamente o mesmo IMPORTANTE AMBOS DEVEM ESTAR CONECTADOS NA MESMA REDE LOCAL.

Vamos programar nosso computador principal pra enviar os dados para raspberry 

```python
# -*- coding: cp1252 -*-
import paho.mqtt.client as mqtt

from time import sleep

topico = "/robot/"


client = mqtt.Client()
# conecta no broker
client.connect("192.168.0.2", 1883)

while True:
    # envia a publicação
    client.publish(topico,"LIGAR LED")
    sleep(1)
    client.publish(topico,"DESLIGAR LED")
    sleep(1)
```

No raspberry pi você deve ter o codigo abaixo para receber os dados publicados

```python
# -*- coding: cp1252 -*-
import paho.mqtt.client as mqtt

from time import sleep

# assinando todas as publicações dentro da area 10
TOPIC = "#"

# função chamada quando a conexão for realizada, sendo
# então realizada a subscrição
def on_connect(self,client, data, rc):
    self.subscribe([(TOPIC,0)])

# função chamada quando uma nova mensagem do tópico é gerada
def on_message(client, userdata, msg):
    # decodificando o valor recebido
    
    #print msg.topic + "/" + str(v)
    
    print "TOPICO: ",msg.topic
    print "payload: ",str(msg.payload)

# clia um cliente para supervisã0
client = mqtt.Client()

# estabelece as funçõe de conexão e mensagens
client.on_connect = on_connect
client.on_message = on_message

# conecta no broker
client.connect("192.168.0.2", 1883)

# permace em loop, recebendo mensagens
client.loop_forever()
```

Teste ! rode os 2  um em cada plataforma e veja como se comporta ^\_^

