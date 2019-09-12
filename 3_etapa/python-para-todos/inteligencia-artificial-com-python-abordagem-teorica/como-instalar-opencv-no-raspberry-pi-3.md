# Como instalar OpenCV no raspberry pi 3 e Zero

### Dependências Básicas 

```bash
sudo apt-get install -y build-essential cmake pkg-config
sudo apt-get install -y libjpeg-dev libtiff5-dev libjasper-dev libpng12-dev
sudo apt-get install -y libavcodec-dev libavformat-dev libswscale-dev libv4l-dev
sudo apt-get install -y libxvidcore-dev libx264-dev
sudo apt-get install -y libgtk2.0-dev
sudo apt-get install -y libatlas-base-dev gfortran
sudo apt-get install -y python2.7-dev python3-dev
```

### Download do OpenCV e Contribuições 

```bash
cd ~
wget -O opencv.zip https://github.com/Itseez/opencv/archive/3.1.0.zip
unzip opencv.zip
 
wget -O opencv_contrib.zip https://github.com/Itseez/opencv_contrib/archive/3.1.0.zip
unzip opencv_contrib.zip
 
```

### Instalação de numpy

```bash
pip install numpy
```

### Entre na Pasta e Crie uma pasta chamada Build

```bash
cd ~/opencv-3.1.0/
mkdir build
cd build
```

### Pre-compile suas configurações

```bash
cmake -D CMAKE_BUILD_TYPE=RELEASE \
    -D CMAKE_INSTALL_PREFIX=/usr/local \
    -D INSTALL_PYTHON_EXAMPLES=ON \
    -D OPENCV_EXTRA_MODULES_PATH=~/opencv_contrib-3.1.0/modules \
    -D BUILD_EXAMPLES=ON \
    -DENABLE_PRECOMPILED_HEADERS=OFF .. #test lesk test ..
```

### Compilação para o RASPBERRY PI 3

```bash
make -j4 
sudo make install
sudo ldconfig
```

### PS: Compilação para o RASPBERRY PI ZERO W 

```bash
make 
sudo make install
sudo ldconfig
```

### FINAL

![](../../../.gitbook/assets/image%20%2822%29.png)

