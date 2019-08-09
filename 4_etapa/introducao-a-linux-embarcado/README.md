---
description: Conhecendo Raspbian e Yocto
---

# Introdução a Linux Embarcado

## O que é Linux Embarcado ?

![Linux Embarcado do Raspberry Pi](../../.gitbook/assets/image%20%2820%29.png)

É a aplicação e uso do kernel Linux em uma placa eletrônica cujo principal elemento é o SoC\(System-on-a-chip\). SoC é um chip eletrônico que reúne todos os elementos básicos de um sistema computacional como CPU, memória principal\(RAM\), memória secundaria\(ROM/FLASH\) e alguns periféricos. Atualmente um SoC contém internamente diversos periféricos dos mais variados tipos como I2C, SPI, UART, CAN, enfim, a lista pode ser enorme. A figura abaixo mostra um típico SoC ARM.

Fora Raspbian tambem vamos conhecer o projeto Yocto

![](../../.gitbook/assets/image%20%2821%29.png)

Esse projeto vem com as principais ferramentas utilizadas para construímos nosso próprio sistema operacional caso precise, contudo vale ressaltar que o principal objetivo dessa ultima etapa é entender como funciona essas distribuições e como aplicar elas em nossos projetos.

Então Vamos estudar Yocto e Raspbian nos próximos 2 tutoriais. 

### Mas onde usamos linux embarcados ?

A resposta é simples em qualquer projeto que precise de um processamento dedicado para algo móvel, como uma plataforma robótica, um carro autônomo, ou até no seu pet para pegar dados de sensores e trata-los, pense que podemos usar mini pcs altamente otimizados como um raspberry para rodar nossos modelos de visão computacional ou usar de servidor para hospedar micro serviços de rede e sites ou até mesmo suas próprias ferramentas.

![Raspberry Pi 4 Model B](../../.gitbook/assets/image%20%2819%29.png)



