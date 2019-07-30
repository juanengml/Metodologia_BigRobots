---
description: vamos usar a ponte h
---

# Controlando Motor de Passo com Shield

### Como funciona uma motor de passos  ?

![](https://uploads.filipeflop.com/2013/12/motor5vlist.jpg)

Este motor é alimentado por 5v, possui uma redução de 1/64 e segundo o [datasheet](http://robocraft.ru/files/datasheet/28BYJ-48.pdf) , são necessários 64 passos para que o motor dê uma volta completa \(5,625º / 64 passos \), isso em modo “puro” \(sem redução\). Com a redução de 1/64 ,o número de passos aumenta para 4096 \(64 \* 64 = 4096\). Esses valores são válidos se utilizarmos o esquema de ativação das bobinas em 8 passos \(half-mode, ou meio-passo\).  Se utilizarmos o esquema de ativação de 4 passos \(full-step, ou passo inteiro\), que é o padrão utilizado pela biblioteca do Arduino, o número de passos necessários cai pela metade, para 2048.

Para entendermos essa diferença, vamos dar uma olhada na tabela abaixo, que mostra o acionamento das bobinas do motor em 8 etapas :

![Motor de passo 28BYJ-48 - Conexoes](https://uploads.filipeflop.com/2013/12/Motor_de_passo_28BYJ_48_Conexoes.png)

![Sequencia de ativacao - 8 passos](https://uploads.filipeflop.com/2013/12/Sequencia_de_ativacao_8_passos.jpg)

Nesse modo, primeiro é acionada uma bobina, depois duas, depois uma novamente, depois duas,  e assim por diante, em 8 etapas. Já no modo de 4 passos, são acionadas 2 bobinas de cada vez, o que reduz o número de acionamentos necessários para girar o motor :

![Sequencia de ativacao - 4 passos](https://uploads.filipeflop.com/2013/12/Sequencia_de_ativacao_4_passos.jpg)

Também no modo 4 passos, teoricamente teremos mais força no motor, pois estamos acionando duas bobinas ao mesmo tempo.

### Circuito

![](https://uploads.filipeflop.com/2013/12/motor-shield-com-motor-de-passo-2byj-481.png)

### Código

```c
 
#include <AFMotor.h>
double passos_total = 2048; //Numero de passos para 1 rotacao total
 
int porta_motor = 2; //1 para motor em M1/M2 e 2 para motor em M3/M4
int angulo = 30; //Angulo de rotacao do eixo
 
double numero_de_passos = 0; //Armazena o numero de passos que o motor vai girar
 
AF_Stepper arduino(passos_total, porta_motor); //Define os parametros do motor
 
void setup()
{
arduino.setSpeed(10); //Define a velocidade de rotacao
Serial.begin(9600);
}
 
void loop()
{
//Calcula a quantidade de passos, baseado no angulo determinado
numero_de_passos = angulo / (360 / passos_total);
 
//Mostra no serial monitor o numero de passos calculados
Serial.println(numero_de_passos);
 
//Move o motor. Use FORWARD para sentido horario,
//BACKWARD para anti-horario
arduino.step(numero_de_passos, FORWARD, SINGLE);
arduino.release();
 
delay(2000);
}
 Gostou? Deixe seu comentário logo
```

### Easy neh ?

![](https://media.giphy.com/media/o0vwzuFwCGAFO/giphy.gif)





