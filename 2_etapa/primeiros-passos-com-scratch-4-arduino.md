# Programação com Scratch 4 Arduino

![](https://images.squarespace-cdn.com/content/56d92cc060b5e9db654d0535/1482430037458-A55285AOKRVAF30PEXNA/S4P+Or+Shoval?content-type=image%2Fgif)



### O que é Scratch 4 Arduino ? 

 S4A é uma modificação do **Scratch** que permite programação simples da plataforma de hardware aberto **Arduino**. Ela provê novos blocos para gerenciar sensores e atuadores conectados ao **Arduino**.

## Sobre S4A

S4A é uma modificação do [Scratch](http://scratch.mit.edu) que permite programação simples da plataforma de hardware aberto [Arduino](http://arduino.cc). Ela provê novos blocos para gerenciar sensores e atuadores conectados ao [Arduino](http://arduino.cc). Há também uma placa de relatório de sensores similar à PicoBoard.

O foco principal deste projeto é atrair pessoas para o mundo da programação. O objetivo também é fornecer uma interface de alto nível para programadores de [Arduino](http://arduino.cc) com funcionalidades tais quais interagir com um conjunto de placas através de eventos de usuários.

### A Interface

 ![](http://s4a.cat/img/shot01.png) _Um programa do S4A que controla um sensor de luz Theremin, com capacidades de gravação e execução_

Objetos do Arduino oferecem blocos para as funcionalidades básicas do microcontrolador, saídas e entradas analógicas e digitais, e também para de alto nível. Você pode encontrar blocos para gerenciar servomotores padrão ou de rotação contínua:

![](http://s4a.cat/img/blocks.png)

Em S4A, uma placa [Arduino](http://arduino.cc) é representada por um tipo especial de figura. A figura do Arduino encontrará automaticamente a porta usb onde a placa está conectada.

É possível conectar múltiplas placas ao mesmo tempo apenas adicionando uma nova figura do Arduino.

### Detalhes técnicos

#### Placas suportadas

S4A funciona com o Arduino Diecimila, Duemilanove e Uno. Outras placas não foram testadas, mas também podem funcionar.

#### Conectividade

Componentes devem ser conectados de uma forma específica. O S4A permite 6 entradas analógicas \(pinos analógicos\), 2 entradas digitais \(pinos digitais 2 e 3\), 3 saídas analógicas \(pinos digitais 5, 6 e 9\), 3 saídas digitais \(pinos 10, 11 e 13\) e 4 saídas especiais para conectar um servomotor de rotação contínua Parallax \(pinos digitais 4, 7, 8 e 12\).

Você pode gerenciar uma placa sem fios adicionando um módulo de RF, como um Xbee.

S4A permite que você controle quantas placas puder conectar nas portas USB de seu computador.

#### Compatibilidade

S4A é retrocompatível com o [Scratch](http://scratch.mit.edu), portanto você pode abrir projetos do [Scratch](http://scratch.mit.edu) nele. Porém, você não poderá compartilhar seus projetos na comunidade no website do [Scratch](http://scratch.mit.edu) pois seria contra os termos de uso do [Scratch](http://scratch.mit.edu) .

Leve em conta que esta compatibilidade não funciona em duas mãos, portanto você não poderá abrir um projeto do S4A pelo [Scratch](http://scratch.mit.edu) original.

Utilizar uma PicoBoard juntamente de uma placa [Arduino](http://arduino.cc) também é suportado.

#### Protocolo

S4A interage com o [Arduino](http://arduino.cc) enviando os estados dos atuadores e recebendo estados dos sensores a cada 75 ms, portanto a largura de pulso necessita ser maior que este período de tempo. A troca de dados segue o protocolo da PicoBoard e precisa de um programa específico \(firmware\) instalado na placa. Por favor use a sessão de Downloads como referência de instruções em como fazer isso.

### Manjando ? Rlx jaja se vai manjar !

![](https://hackster.imgix.net/uploads/attachments/324112/yagajfz_ipb4OShnPf.gif?auto=compress&gifq=35&w=600&h=450&fit=min)







