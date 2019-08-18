# Topologia de Redes de computadores

### O que significa o termo topologia

 Uma rede informática é constituída por computadores conectados entre eles graças a linhas de comunicação \(cabos de redes, etc.\) e elementos de hardware \(placas de rede ou outros equipamentos que garantem a boa circulação dos dados\). O arranjo físico, ou seja, a configuração espacial da rede chama-se **topologia física**. Geralmente, distinguimos as seguintes topologias: rede em barramento, rede em estrela, rede em anel, rede em árvore e rede de malha \(ou mesh\).  
  
A **topologia lógica**, em oposição à topologia física, representa a forma como os dados transitam nas linhas de comunicação. As topologias lógicas mais correntes são a [Ethernet](https://br.ccm.net/contents/673-ethernet), o Token Ring e o [FDDI](https://br.ccm.net/contents/674-fddi-fiber-distributed-data-interface).

### Rede em estrela

 Numa **rede em estrela**, os computadores da rede estão ligados a um sistema material central chamado **concentrador** \(hub, em inglês\). Trata-se de uma caixa com diversas junções às quais se podem conectar os cabos provenientes dos computadores. Seu papel é garantir a comunicação entre as diferentes junções:

![](https://thumbs.gfycat.com/CooperativeShrillGavial-size_restricted.gif)

  
  
Contrariamente às redes em barramento, as redes em estrela são muito menos vulneráveis porque uma das conexões pode ser desligada do concentrador sem, por isso, paralisar o resto da rede. O ponto nevrálgico desta rede é o hub, porque sem ele nenhuma comunicação entre os computadores da rede pode ser feita.  
  
Por outro lado, uma rede em estrela é mais cara do que uma rede em barramento, já que ela requer um hardware suplementar \(o hub\).

### Rede de malha ou mesh

 Uma **rede mesh**, é uma evolução da rede em estrela, ela corresponde à várias conexões ponto a ponto. Uma unidade de rede pode ter \(1, N\) conexões ponto a ponto com várias outras unidades. Cada terminal é conectado a todos os outros. A desvantagem é o grande número de conexões necessárias.  
  
Esta topologia é encontrada em grandes redes de distribuição \(ex: Internet\). As informações podem navegar na rede seguindo rotas diversas, sob o controle de poderosos supervisores de rede ou através de métodos distribuídos de roteamento. O Exército também usa esta topologia, assim, em caso de quebra de um link, as informações ainda podem ser enviadas. Ela também existe em caso de cobertura Wi-Fi. Isso é chamado de rede de malha mas só diz respeito aos roteadores Wi-Fi:  
  


![](../../.gitbook/assets/image%20%2811%29.png)



#### Fonte

{% embed url="https://br.ccm.net/contents/258-topologia-de-redes" %}





