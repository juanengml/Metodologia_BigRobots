---
description: >-
  Nesse projeto vamos construir um sisteminha simples para ler dados de sensor e
  mostrar se a lampada está ou não ligada.
---

# Sistema de Monitoramento de Luminosidade em Laboratórios.

### Descrição

Aqui vamos usar a plata nodemcu pra conectar na rede wifi local e pegar dados de luminosidade e enviar esses dados para nosso servidor local e poder visualizar esses dados em nossa dashboard interativa {^\_^}

### Circuito

![](http://osoyoo.com/wp-content/uploads/2016/12/ppppppp.png)

### Crie seu Dispositivo na Thingsboard





### Código



```c
#include <ESP8266WiFi.h>
#include <ThingsBoard.h>

#define WIFI_AP "YOUR_WIFI_AP"
#define WIFI_PASSWORD "YOUR_WIFI_PASSWORD"

#define TOKEN "ESP8266_DEMO_TOKEN"

// DHT

char thingsboardServer[] = "YOUR_THINGSBOARD_HOST_OR_IP";

WiFiClient wifiClient;

// Initialize DHT sensor.


ThingsBoard tb(wifiClient);

int status = WL_IDLE_STATUS;
unsigned long lastSend;

void setup()
{
  Serial.begin(115200);
  dht.begin();
  delay(10);
  InitWiFi();
  lastSend = 0;
}

void loop()
{
  if ( !tb.connected() ) {
    reconnect();
  }

  if ( millis() - lastSend > 1000 ) { // Update and send only after 1 seconds
    Pegar_Enviar_dadoDeLuminosidade();
    lastSend = millis();
  }

  tb.loop();
}

void Pegar_Enviar_dadoDeLuminosidade()
{
  Serial.println("Collecting temperature data.");

  float luminosidade= analogRead(A0);

  if (isnan(luminosidade)) {
    Serial.println("Failed to read from sensor!");
    return;
  }
  Serial.println("Luminosidade:  [");
  Serial.print(luminosidade);
  Serial.println("]  ");

  tb.sendTelemetryFloat("luminosidade", luminosidade);
}

void InitWiFi()
{
  Serial.println("Connecting to AP ...");
  // attempt to connect to WiFi network

  WiFi.begin(WIFI_AP, WIFI_PASSWORD);
  while (WiFi.status() != WL_CONNECTED) {
    delay(500);
    Serial.print(".");
  }
  Serial.println("Connected to AP");
}


void reconnect() {
  // Loop until we're reconnected
  while (!tb.connected()) {
    status = WiFi.status();
    if ( status != WL_CONNECTED) {
      WiFi.begin(WIFI_AP, WIFI_PASSWORD);
      while (WiFi.status() != WL_CONNECTED) {
        delay(500);
        Serial.print(".");
      }
      Serial.println("Connected to AP");
    }
    Serial.print("Connecting to ThingsBoard node ...");
    if ( tb.connect(thingsboardServer, TOKEN) ) {
      Serial.println( "[DONE]" );
    } else {
      Serial.print( "[FAILED]" );
      Serial.println( " : retrying in 5 seconds]" );
      // Wait 5 seconds before retrying
      delay( 5000 );
    }
  }
}
```



Dashboard 

Visualização

