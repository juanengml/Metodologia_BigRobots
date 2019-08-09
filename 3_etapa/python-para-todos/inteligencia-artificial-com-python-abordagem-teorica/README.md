---
description: >-
  Vamos estudar os principais modelos ciências de dados e inteligencia
  artificial
---

# Inteligência Artificial com Python

## Tipo de problemas

Em nossa metodologia vamos aprender a resolver 2 tipos de problemas, problemas de classificação e regressão. Uma vai classificar como SIM ou NÃO, determinado tipo de problema e o outro vai prever algum valor numerico, do tipo "O robo preve que em 2 horas vai precisar carregar a bateria se continuar com o consumo em valor de 60% de bateria".

![](https://i0.wp.com/www.cienciaedados.com/wp-content/uploads/2018/06/ia.png?resize=900%2C572)

## Regressão x Classificação

![](https://cultura.estadao.com.br/blogs/estado-da-arte/wp-content/uploads/sites/426/2018/06/figura1-768x216.jpeg)

Em regressão temos retorno de valores numericos para prever preço de imoveis, gasolina, idade, estimar preço do dolar.

Classificação temos rotulos normalmente binarios do tipo, tem ou não um gato na imagem ?, sim ou não, podemos classificar niveis de umidade solo como: umido, seco, molhado, arido. 

## Bibliotecas usadas Sklearn e OpenCV

![](../../../.gitbook/assets/image%20%282%29.png)

Sklearn é uma biblioteca base para entendermos e trabalharmos com os modelos mais basicos e completos de inteligencia artificial, nela temos todos os modelos e codigos de exemplo para usarmos em nossas aplicações.

Para instalar o sklearn no seu linux basta digitar.

```bash
$ pip install sklearn
```

![](../../../.gitbook/assets/image%20%2818%29.png)

OpenCV É um framework que permite usarmos para aplicações que envolvam trabalhar como imagens, cameras e videos. Com ela podemos construir nossos modelos de detecção de rostos, contar linhas, detecar pessoas em ambientes, podemos usar ela para construir nossos proprios modelos de reconhecimento de objetos personalizados.

Para instalar o opencv em seu computador basta digitar o codigo abaixo.

```bash
$ pip install opencv-python
```

#### PS: Caso queira instalar o opencv em um raspberry consulto o link abaixo

{% page-ref page="como-instalar-opencv-no-raspberry-pi-3.md" %}

## KNN\(K - DISTANCIA DE VIZINHOS\)

![](https://thumbs.gfycat.com/WildSorrowfulChevrotain-size_restricted.gif)

Não importa se o problema de aprendizado de máquina é adivinhar um número ou uma classe, a idéia por trás da estratégia de aprendizado do algoritmo k-Nearest Neighbors \(kNN\) é sempre a mesma. O algoritmo encontra as observações mais similares àquelas que você tem que prever e das quais você obtém uma boa intuição da resposta possível, calculando a média dos valores vizinhos, ou escolhendo a classe de respostas mais frequente entre eles.

### Código de Exemplo

```python
>>> X = [[0], [1], [2], [3]]
>>> y = [0, 0, 1, 1]
>>> from sklearn.neighbors import KNeighborsClassifier
>>> vizinho = KNeighborsClassifier(n_neighbors=3)
>>> vizinho.fit(X, y) 
>>> print(vizinho.predict([[1.1]]))
[0]
>>> 
```

#### Documentação em Inglês

{% embed url="https://scikit-learn.org/stable/modules/generated/sklearn.neighbors.KNeighborsClassifier.html" %}

## K-MEAN\(GRUPO DE VIZINHOS\)

![](https://i.imgur.com/wcpFFiu.gif)

Você geralmente implanta algoritmos k-means para subdividir pontos de dados de um conjunto de dados em clusters com base nos valores médios mais próximos. Para determinar a divisão ideal de seus pontos de dados em clusters, de modo que a distância entre pontos em cada cluster seja minimizada, você pode usar o clustering k-means.

### Código de Exemplo

```python
from sklearn.cluster import KMeans
import numpy as np
X = np.array([[1, 2], [1, 4], [1, 0],
              [10, 2], [10, 4], [10, 0]])
kmeans = KMeans(n_clusters=2, random_state=0).fit(X)
kmeans.labels_

kmeans.predict([[0, 0], [12, 3]])

kmeans.cluster_centers_
```

#### Documentação em Inglês

{% embed url="https://scikit-learn.org/stable/modules/generated/sklearn.cluster.KMeans.html" %}



## SVM\(SUPORT VECTOR MACHINE\)

![](https://miro.medium.com/max/1200/1*Hz76FfcofSRNPLJUZR6YKg.gif)

Uma Máquina de Vetor de Suporte \(SVM\) é um algoritmo de aprendizado de máquina supervisionado que pode ser empregado para propósitos de classificação e regressão. SVMs são mais comumente usados ​​em problemas de classificação. Ele divive os dados e cria um plano no meio dos dados para poder classificar.

Os vetores de suporte são os pontos de dados mais próximos ao hiperplano, os pontos de um conjunto de dados que, se removidos, alterariam a posição do hiperplano divisor. Por causa disso, eles podem ser considerados os elementos críticos de um conjunto de dados.

### Código de Exemplo

```python
>>> from sklearn import svm  # importamos 
>>> X = [[0, 0], [1, 1]]  # definimos dados de treino
>>> y = [0, 1]            # definimos dados de rotulo
>>> classificador = svm.SVC(gamma='scale')
>>> classificador.fit(X, y) # treino do modelo
>>> classificador.predict([[2., 2.]])  # testando nosso modelo
array([1])
```

#### Documentação em Inglês

{% embed url="https://scikit-learn.org/stable/modules/svm.html" %}





