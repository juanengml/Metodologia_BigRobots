---
description: Vamos controlar um motor dc usando um modulo chamado ponte h
---

# Brincando com Motor DC

### O que é uma ponte H ?

Ponte H é um circuito de eletrônica de potência do tipo chopper de classe E, e, portanto, pode determinar o sentido da corrente, a polaridade da tensão e a tensão em um dado sistema ou componente. **Volto controlar motores para nozes aqui {^\_^}**

![](https://uploads.filipeflop.com/2017/07/Arduino-motor-shield-l293d.png)

\*\*\*\*

### Descrição 

Nesse tutorial vamos usar um ponte h shield, que permite controlemos 4 motores ela é excelente para controlar motores de robôs. **Motor Shield L293D Driver Ponte H para Arduino**

Este é o Motor Shield L293D integrando alta tensão, alta corrente e controle de 4 canais em uma só placa! ****

Este é o Motor Shield L293D integrando alta tensão, alta corrente e controle de 4 canais em uma só placa! Basicamente isto significa que você pode ligar motores DC e uma fonte de tensão de até 16v que este chip se encarrega de fornecer uma corrente máxima de 600mA por canal. O chip L293D também é conhecido como um tipo de Ponte H que é tipicamente um circuito elétrico que permite uma tensão ser aplicada em uma carga em qualquer direção para uma saída, como por exemplo um motor.

Este Arduino Motor Shield é baseado no chip L293D e com ele é possível controlar até **4 Motores DC, 2 Servos ou 2 Motores de Passo!** 

O chip L293D possui internamente 2 Ponte H e suporta uma corrente de saída de 600mA por canal, ou seja, será possível controlar até 2 motores com 600mA cada, visto que neste Shield temos 2 chips. Tensão suportada de 4,5-16V.

**Especificações:**  
– Chip: 293D \([Datasheet](https://arduino.cc/documents/datasheets/L293D.pdf)\)  
– Pode controlar 4 Motores DC, 2 Motores de Passo ou 2 Servos.  
– Tensão de saída: 4,5-16V  
– Corrente de saída: 600mA por canal  
– Até 4 motores DC bi-direcional com seleção individual de velocidades de 8 bits \(cerca de 0,5% de resolução\).  
– Até 2 Motores de Passo \(Unipolar ou Bipolar\) com bobina unica, dupla ou passos interlaçados.  
– 4 Pontes H: 0,6A por Ponte \(1,2A de pico\) com proteção térmica e diodos de proteção contra retro-alimentação.  
– Resistores Pull Down mantem motores desativos durante a entrada de alimentação.  
– Botão de Reset Arduino disponível no topo da placa.  
– Terminais em bloco de 2 pinos e jumper para conexão de alimentação externa.

### Como usar para controlar um motor DC **?**

### Circuito 

![](https://3.bp.blogspot.com/-5sQOwm0HBm4/U7SkhiRxJeI/AAAAAAAACZc/_NvH0NUnRRc/s1600/Circuito-2-motores-DC-Motor-Shield-L293D.png)



### Código

```c
#include <AFMotor.h>
// Define o motor1 ligado a conexao 1
AF_DCMotor motor1(1); 
// Define o motor2 ligado a conexao 4
AF_DCMotor motor2(4); 
 
void setup()
{
  // Define a velocidade maxima para os motores 1 e 2
  motor1.setSpeed(255); 
  motor2.setSpeed(255); 

}
 
void loop()
{
  // Aciona o motor 1 no sentido horario
  motor1.run(FORWARD); 
  // Aciona o motor 2 no sentido anti-horario
  motor2.run(BACKWARD); 
 
  // Aguarda 5 segundos
  delay(5000);

  // Desliga os 2 motores
  motor1.run(RELEASE); 
  motor2.run(RELEASE); 

  // Aciona o motor 1 no sentido anti-horario
  motor1.run(BACKWARD);
  // Aciona o motor 2 no sentido horario
  motor2.run(FORWARD); 
 
  // Aguarda 5 segundos
  delay(5000);
  
  // Desliga os 2 motores
  motor1.run(RELEASE); 
  motor2.run(RELEASE);
}

```

### Teste de Mesa !

![](https://media2.giphy.com/media/KURFE7gU3qJuE/giphy.gif)







