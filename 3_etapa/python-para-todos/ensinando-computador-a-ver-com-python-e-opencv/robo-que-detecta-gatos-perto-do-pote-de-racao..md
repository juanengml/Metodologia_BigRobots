# Robô que Detecta gatos perto do pote de ração.

### Faça download do classificador abaixo

{% embed url="https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade\_frontalcatface.xml" %}

Em seguida podemos ir direto para o código, contudo caso queira entender como funciona o treinamento de um classificador como este clique no link abaixo.

{% embed url="https://www.instructables.com/id/Haar-Cascade-Python-OpenCV-Treinando-E-Detectando-/" %}

### Caso prefira ir para o codigo....let's CODE !!!! 

```python
# -*- coding: utf-8 -*-
import cv2

x=0
y=0

cascPath = "haarcascade_frontalcatface.xml"
faceCascade = cv2.CascadeClassifier(cascPath)
font=cv2.FONT_HERSHEY_SIMPLEX
#video_capture = cv2.VideoCapture(1)
video_capture = cv2.VideoCapture("movie.avi")

while True:
    ret, frame = video_capture.read()
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    faces = faceCascade.detectMultiScale(
        gray,
        scaleFactor=1.1,
        minNeighbors=5,
        minSize=(50, 50),)
    if len(faces) >= 1:
     print "Face detect"
     cv2.putText(img = frame, text = 'Body found:' + str(len(faces)), org=(50,50), fontFace=cv2.FONT_HERSHEY_DUPLEX, fontScale=1, color=(0, 0, 255))
     for (x, y, w, h) in faces:
        cv2.rectangle(frame, (x, y), (x+w, y+h), (0, 255, 100), 1)
        stringxy="+%s,%s"%(x,y) # To prepare the string with the xy values to be used with the cv2.putText function
        cv2.putText(frame,stringxy,(x+w/2,y+h/2),font, 1,(0,0,255),1)

    else:
        print "Not body "
    cv2.imshow('Video', frame)
    font=cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(faces,'x,y',(x,y),font, 2,(255,255,255),1)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
video_capture.release()
cv2.destroyAllWindows()

```

Da Linha 2 a 11 

Nos importamos a biblioteca opencv, definimos x e y como variaveis zeradas para utilização posteriormente, definimos o nome do nosso arquivo classificador, criamos uma instancia do arquivo com a funcção cv2.CascadeClassifier e em font definimos a font padrão para visualização.

```python
import cv2

x=0
y=0

cascPath = "haarcascade_frontalcatface.xml"
faceCascade = cv2.CascadeClassifier(cascPath)
font=cv2.FONT_HERSHEY_SIMPLEX
#video_capture = cv2.VideoCapture(1)
video_capture = cv2.VideoCapture("movie.avi")

```

Em video capture utilizamos um video para test e detectar o a face do gato

Em seguida dentro do nosso laço utilizamos a função read para pegar dados de ret e frame, com os dados de frame convertemos a imagem para cinza e passamos o parametro faceCascade.detectMultiScale com os hiper parametros de ajuste. 

```python
while True:
    ret, frame = video_capture.read()
    gray = cv2.cvtColor(frame, cv2.COLOR_BGR2GRAY)
    faces = faceCascade.detectMultiScale(
        gray,
        scaleFactor=1.1,
        minNeighbors=5,
        minSize=(50, 50),)
```

Com esses dados caso o numero de faces seja maior que 1 contabiliza que tem um gato na imagem e desenha um retangulo na area que pertence ao que representação o gato detectado.

```python

    if len(faces) >= 1:
     print "Face detect"
     cv2.putText(img = frame, text = 'cat found:' + str(len(faces)), org=(50,50), fontFace=cv2.FONT_HERSHEY_DUPLEX, fontScale=1, color=(0, 0, 255))
     for (x, y, w, h) in faces:
        cv2.rectangle(frame, (x, y), (x+w, y+h), (0, 255, 100), 1)
        stringxy="+%s,%s"%(x,y) # To prepare the string with the xy values to be used with the cv2.putText function
        cv2.putText(frame,stringxy,(x+w/2,y+h/2),font, 1,(0,0,255),1)

    else:
        print "cat not found"
```

Caso nada seja detectado apenas imprime uma mensagem na tela de não encontrado.

E então a imagem é mostrada na interface usando a função imshow e escreve a tela os dados da face em x e y, para sair tecle 'q' e o programa vai fechar.

```python
    cv2.imshow('Video', frame)
    font=cv2.FONT_HERSHEY_SIMPLEX
    cv2.putText(faces,'x,y',(x,y),font, 2,(255,255,255),1)
    if cv2.waitKey(1) & 0xFF == ord('q'):
        break
video_capture.release()
cv2.destroyAllWindows()

```

![](https://www.pyimagesearch.com/wp-content/uploads/2016/05/cat_face_detector_result_01.jpg)



