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

# Cuda
https://developer.nvidia.com/cuda-80-ga2-download-archive
```
sudo dpkg -i cuda-repo-ubuntu1404-8-0-local-ga2_8.0.61-1_amd64.deb
sudo apt-get update
sudo apt-get install cuda
```
