---
description: Nível = Intermediário
---

# Tutorial Display LCD Nokia  5110

### Descrição Display Nokia

O display LCD é uma interface de comunicação visual e está presente em muitos aparelhos domésticos, eletroeletrônicos, automóveis e instrumentos de medição.

O **Display LCD 84×48 Nokia 5110** possui 84 colunas e 48 linhas, além disso, também possui backlight \(fundo\) branco. O grande diferencial do **Display LCD 84×48 Nokia 5110** está na sua capacidade de exibir conteúdos gráficos. Em projetos com arduino \(ou outros microcontroladores\) pode ser utilizado em processos onde será necessário exibir informações em tempo real, tais como temperatura, umidade, valor de tensão ou corrente, mensagens de erro, imagens gráficas e etc.

### Código

```c
#include <SPI.h> //INCLUSÃO DE BIBLIOTECA
#include <Adafruit_GFX.h> //INCLUSÃO DE BIBLIOTECA
#include <Adafruit_PCD8544.h> //INCLUSÃO DE BIBLIOTECA
 
//OBJETO DO TIPO Adafruit_PCD8544 COM OS PARÂMETROS (PINOS)
Adafruit_PCD8544 display = Adafruit_PCD8544(6, 5, 4, 3, 8);
 
int rotatetext = 0; //VARIÁVEL DE CONTROLE DA ROTAÇÃO DO TEXTO NO DISPLAY
 
void setup(){
  Serial.begin(9600); //INICIALIZA A SERIAL
  display.begin(); //INICIALIZA O DISPLAY
  display.setContrast(20); //DEFINE O CONTRASTE DO DISPLAY
  display.clearDisplay(); //LIMPA AS INFORMAÇÕES DO DISPLAY
  display.display(); //EFETIVA A ESCRITA NO DISPLAY
}
 
void loop(){
  
  /*EXIBE TEXTO SIMPLES*/
  
  display.setTextSize(1); //DEFINE O TAMANHO DA FONTE DO TEXTO
  display.setTextColor(BLACK); //DEFINE A COR DO TEXTO
  display.setCursor(0,0); //POSIÇÃO EM QUE O CURSOR IRÁ FAZER A ESCRITA (COLUNA,LINHA)
  display.println("Ola Mundo!"); //ESCREVE O TEXTO NO DISPLAY
  display.display(); //EFETIVA A ESCRITA NO DISPLAY
  delay(2000); //INTERVALO DE 2 SEGUNDOS
  display.clearDisplay(); //LIMPA AS INFORMAÇÕES DO DISPLAY
 }
```

### Circuito

![Fonte: blogmasterwalkershop.com.br](http://blogmasterwalkershop.com.br/wp-content/uploads/2019/06/img03_como_usar_com_arduino_-_display_lcd_84x48_nokia_5110_3.3v_5v_conversor_nivel_logico_divisor_tensao_vermelho_azul_resistor.jpg)





