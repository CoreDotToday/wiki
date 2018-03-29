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

# Cuda Version
## Cuda 8.0
https://developer.nvidia.com/cuda-80-ga2-download-archive

`sudo apt install nvidia-381`
`sudo apt install nvidia-cuda-dev`

`sudo dpkg -i cuda-repo-ubuntu1404-8-0-local-ga2_8.0.61-1_amd64.deb`
`sudo apt-get update`
`sudo apt-get install cuda`

## Cuda 9.0
https://developer.nvidia.com/cuda-90-download-archive?target_os=Linux&target_arch=x86_64&target_distro=Ubuntu&target_version=1604&target_type=debnetwork

`sudo dpkg -i cuda-repo-ubuntu1604_9.0.176-1_amd64.deb`
`sudo apt-key adv --fetch-keys http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/7fa2af80.pub`
`sudo apt-get update`
`sudo apt-get install cuda-9.0`
`sudo apt-get install cuda-toolkit-9.0`

## Current version check
`$ nvcc --version`
```
nvcc: NVIDIA (R) Cuda compiler driver
Copyright (c) 2005-2017 NVIDIA Corporation
Built on Fri_Nov__3_21:07:56_CDT_2017
Cuda compilation tools, release 9.1, V9.1.85
```

`$ pip show tensorflow-gpu`
```
Name: tensorflow-gpu
Version: 1.6.0
Summary: TensorFlow helps the tensors flow
Home-page: https://www.tensorflow.org/
Author: Google Inc.
Author-email: opensource@google.com
License: Apache 2.0
Location: ~~~/lib/python3.6/site-packages
Requires: wheel, grpcio, six, gast, absl-py, astor, protobuf, termcolor, numpy, tensorboard
```

# Cuda Settings
## .bashrc
```
# NVIDIA
export PATH="/usr/local/cuda-8.0/bin:$PATH"
export LD_LIBRARY_PATH="/usr/local/cuda-8.0/lib64:$LD_LIBRARY_PATH"
export LD_LIBRARY_PATH="/usr/local/cuda/lib64:$LD_LIBRARY_PATH"
```

## .bashrc
```
export CUDA_HOME=/usr/local/cuda
export CUDNN=/usr/local/cuDNN
export LD_LIBRARY_PATH=$CUDA_HOME/lib64:$LD_LIBRARY_PATH
export LD_LIBRARY_PATH=$CUDNN/lib64:$LD_LIBRARY_PATH
```


# cuDNN
https://developer.nvidia.com/cudnn
### a Tar File
```
tar -xzvf cudnn-9.0-linux-x64-v7.tgz
sudo cp cuda/include/cudnn.h /usr/local/cuda/include
sudo cp cuda/lib64/libcudnn* /usr/local/cuda/lib64
sudo chmod a+r /usr/local/cuda/include/cudnn.h
```

### a Debian File
```
sudo dpkg -i libcudnn7_7.0.3.11-1+cuda8.0_amd64.deb
sudo dpkg -i libcudnn7-dev_7.0.3.11-1+cuda8.0_amd64.deb
sudo dpkg -i libcudnn7-doc_7.0.3.11-1+cuda8.0_amd64.deb
```

### Test
```
cp -r /usr/src/cudnn_samples_v7/ $HOME
cd $HOME/cudnn_samples_v7/mnistCUDNN
make clean & make
```