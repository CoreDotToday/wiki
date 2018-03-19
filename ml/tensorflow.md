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

`sudo apt install nvidia-381`
`sudo apt install nvidia-cuda-dev`

`sudo dpkg -i cuda-repo-ubuntu1404-8-0-local-ga2_8.0.61-1_amd64.deb`
`sudo apt-get update`
`sudo apt-get install cuda`

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

## cuDNN
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