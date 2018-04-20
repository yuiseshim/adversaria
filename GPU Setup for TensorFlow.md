## Tensorflow on GPU

1. CUDA
1. cuDNN
1. TensorFlow-gpu


## Check GPU
```
lspci | grep -i nvidia
```

## CUDA
Download the cuda-toolkit
> https://developer.nvidia.com/cuda-toolkit
> http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/

## cuDNN
Create the account
> https://developer.nvidia.com/rdp/cudnn-download
```
# Install Runtime library
sudo dpkg -i libcudnn7_7.0.2.38-1+cuda8.0_amd64.deb
# Install developer library
sudo dpkg -i libcudnn7-dev_7.0.2.38-1+cuda8.0_amd64.deb
# Install code samples and user guide
sudo dpkg -i libcudnn7-doc_7.0.2.38-1+cuda8.0_amd64.deb
tar xzvf cudnn-8.0-linux-x64-v5.1.tgz
sudo cp -a cuda/lib64/* /usr/local/cuda-8.0/lib64/
sudo cp -a cuda/include/* /usr/local/cuda-8.0/include/
sudo ldconfig
```

## CUDA and cuDNN paths
```php:hello.php
export PATH=/usr/local/cuda-8.0/bin:${PATH}  
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64:${LD_LIBRARY_PATH}
```
