# Criando um Detector de Presença com webcam

Sala sem sistema.

![](http://i.stack.imgur.com/fchk5.jpg)

Sala com sistema mal calibrado.

![](https://i.stack.imgur.com/PALba.jpg)

### Aqui vamos aprender a como criar um sistema pra detectar pessoas em uma sala, usando o que apredemos no tutorial anterior usando haarcascade de silhueta de pessoas e detecção de faces.

## O Haarcascade que vamos utilizar são esses 2.

### Silhueta de pessoas.

{% embed url="https://github.com/imhighoncoffee/body-detection-haar/blob/master/haarcascade\_fullbody.xml" %}

### Detecção de Faces

{% embed url="https://github.com/opencv/opencv/blob/master/data/haarcascades/haarcascade\_frontalface\_default.xml" %}

OK, com os dois em mãos vamos para o mais simples que é utilizar para detecção de faces.

```python
import numpy as np
import cv2

faceCascade = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')

cap = cv2.VideoCapture(0)

while True:
    ret, img = cap.read()
    img = cv2.flip(img, -1)
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    faces = faceCascade.detectMultiScale(
        gray,        
        scaleFactor=1.2,
        minNeighbors=5,     
        minSize=(20, 20)
    )
    for (x,y,w,h) in faces:
        cv2.rectangle(img,(x,y),(x+w,y+h),(255,0,0),2) 
    cv2.imshow('video',img)

    k = cv2.waitKey(30) & 0xff
    if k == 27: # press 'ESC' to quit
        break

cap.release()
cv2.destroyAllWindows()
```

Viu como é simples ? 

Agora quando formos aplicar usando o classificador de silhueta basta trocar a linha 4 de frontalface para haar cascade full body xml

```python
classificador = cv2.CascadeClassifier('haarcascade_fullbody.xml')
```

Viu ? 

No codigo deve ficar assim



```python
import numpy as np
import cv2

classificador = cv2.CascadeClassifier('haarcascade_frontalface_default.xml')

cap = cv2.VideoCapture(0)

while True:
    ret, img = cap.read()
    img = cv2.flip(img, -1)
    gray = cv2.cvtColor(img, cv2.COLOR_BGR2GRAY)
    silhueta= classificador.detectMultiScale(
        gray,        
        scaleFactor=1.2,
        minNeighbors=5,     
        minSize=(20, 20)
    )
    
    if len(silhueta) >= 1: print "Tem gente na sala".
    else: print "Sala vazia"
    
    for (x,y,w,h) in silhueta:
        cv2.rectangle(img,(x,y),(x+w,y+h),(255,0,0),2) 
    cv2.imshow('video',img)

    k = cv2.waitKey(30) & 0xff
    if k == 27: # press 'ESC' to quit
        break

cap.release()
cv2.destroyAllWindows()
```

Viu como é simples ? que tal agora você testar outros classificadores ? 

Olhe o link e veja os que existem.

{% embed url="https://github.com/opencv/opencv/tree/master/data/haarcascades" %}



