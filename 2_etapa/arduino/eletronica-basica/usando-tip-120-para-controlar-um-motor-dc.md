# Usando TIP 120 para Controlar um Motor DC

### Circuito com 1 Motor

![](../../../.gitbook/assets/tip120-solenoid.png)

### Código em C



```c
int tip = 9;

void setup(){
 pinMode(tip,OUTPUT);
}
void loop(){
 digitalWrite(tip,HIGH);
 delay(1000);
 digitalWrite(tip,LOW);
 delay(1000);
}
```

### Circuito com 2 Motores

![](../../../.gitbook/assets/screenshot_2019-08-16-autodesk-circuits.png)

### Itens Utilizados 

| Descrição | compoentes |
| :--- | :--- |
| Controlador Logico | Arduino UNO |
| Transistor tipo NPN | TIP 120 |
| Atuador | Motor DC com Caixa de Redução |
| Bateria | Bateria de 9v |

### Código em Blocos

![](../../../.gitbook/assets/screenshot_2019-08-16-autodesk-circuits-1.png)

### Simulação

{% embed url="https://www.tinkercad.com/things/2bWm9HssfPw-controlador-de-motores-com-tip120/" %}



