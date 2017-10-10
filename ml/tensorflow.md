<!-- TITLE: Tensorflow -->
<!-- SUBTITLE: A quick summary of Tensorflow -->

# Installation
https://www.tensorflow.org/install/
```
$ conda create -n tf python=3.5
$ source activate tf
$ pip install https://storage.googleapis.com/tensorflow/linux/gpu/tensorflow_gpu-1.3.0-cp35-cp35m-linux_x86_64.whl # https://www.tensorflow.org/install/install_linux
$ python3 -c 'import tensorflow as tf; print(tf.__version__)'
1.3.0
```