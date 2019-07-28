# Criando App para controlar um led com Bluetooth\(parte 2\)

### PS: Se sentir dificuldades peça ajuda para um superior.

### Materiais Utilizados

| Item | Descrição |
| :--- | :--- |
| LED | Led vai ligar ou desligar |
| HC-06 | Bluetooth |
| Arduino Uno | Placa controladora |

### Circuito

![](https://cdn.instructables.com/FZW/022P/I8SLPBAD/FZW022PI8SLPBAD.LARGE.jpg)

![Assim que voc&#xEA; energizar ele vai piscar assim.](http://www.buildlog.net/blog/wp-content/uploads/2017/10/blink_hc-06.gif)



### Código

```c
int led = 13;
char cmd;
void setup(){
 Serial.begin(9600);
 pinMode(led,OUTPUT);
}

void loop(){
 cmd = Serial.read();
 switch(cmd){
 case 'a':
  // QUando receber letra l liga led 
  digitalWrite(led,HIGH);
 break;
 
 case 'd':
   // QUando receber letra d desliga led 
   digitalWrite(led,LOW);
 break;
}
```

### Teste de Mesa



