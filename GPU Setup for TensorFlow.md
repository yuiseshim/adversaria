## Tensorflow on GPU

- CUDA
- cuDNN
- TensorFlow-gpu


### Check GPU
lspci | grep -i nvidia

### CUDA
- Download the cuda-toolkit
> https://developer.nvidia.com/cuda-toolkit
> http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/

### cuDNN
- Create the account
> https://developer.nvidia.com/rdp/cudnn-download


### Path
#### CUDA and cuDNN paths
export PATH=/usr/local/cuda-8.0/bin:${PATH}
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64:${LD_LIBRARY_PATH}
