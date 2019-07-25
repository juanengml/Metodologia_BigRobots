# Usando Modulo relê para controlar uma lampada

### Descrição do Modulo relê

Este modulo Relé 5V com 1 canal é a alternativa perfeita pra quem busca um módulo compacto e de qualidade para projetos com Arduino e outros controladores.



### Código



```c
int tip = 3;

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

### Circuito

### Teste de Mesa

