# Usando Python com Arduino

Para esse tutorial vamos usar uma lib maravilhosa **PySerial**. 

Antes de tudo vamos instalar a biblioteca. 

```bash
$ pip install pyserial
```

Agora sim, vamos estudar ! 

Primeiramente precisamos ter um codigo rodando no nosso arduino. De exemplo vamos rodar esse código simplão. No nosso arduino para poder pegar dados do sensor.

## Usando Python para ler dados de sensores do Arduino para o Python

![](https://1.bp.blogspot.com/-b0N4NYoM3g0/WIJVUxZlNdI/AAAAAAAAFWo/plZwqhTJd0oPd7Y08DAmVR0QfXG3BxRhQCEw/s1600/PyArdu.png)



### Circuito Arduino

![](https://blog.udemy.com/wp-content/uploads/2014/05/LDR1-1-620x436.png)

### Código Arduino

```c
int ldr  = A0; // sensor de luminosidade
int sensor;
void setup(){
 Serial.begin(9600);
 pinMode(ldr,INPUT);
}

void loop(){
  sensor = analogRead();
  Serial.println(sensor);
  delay(100);
}
```

Ok, depois que seu codigo está no arduino, agora vamos olhar para nosso python.

### Código Python

```python
import serial 

arduino = serial.Serial("/dev/ttyACM0",9600) 
# se o seu arduino for original vai criar a porta semelhante há essa.
# se for alternativo, vai ser ttyUSB0 ou algo assim.

while True:
   print arduino.readline()
```

Viu como é simples ? Agora vamos controlar um led com python.

## Usando python para controlar o arduino.

### Circuito do Arduino 

![](https://d2pgkqk54rmkqw.cloudfront.net/wp-content/uploads/2016/04/Blink_Big_LED.gif)

### Código Arduino

```c
int led = 13;
char cmd;
void setup()
{
   pinMode(led,OUTPUT);
   Serial.begin(9600);
}
void loop()
{
   cmd = Serial.read(); // ler entrada na porta serial
   switch(cmd){
   case 'l':  // caso o python envie letra l liga led
      digitalWrite(led,HIGH);
   break;
   
   case 'd': // caso o python envie letra d desliga o led
      digitalWrite(led,LOW);
   break;
   }
}
```

### Código Python

```python
import serial
from time import sleep # Biblioteca para dar um delay com python.
arduino = serial.Serial("/dev/ttyUSB0",9600)

while True:
   arduino.write('l') # envia letra l para o arduino e liga o led
   sleep(1) # espera 1 segundo
   arduino.write('d') # envia letra d para o arduino e desliga o led
   sleep(1) # espera 1 segundo
```

Oi ? Se viu como é Simples fazer as coisas em python ? 

