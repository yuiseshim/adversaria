## Tensorflow on GPU

- CUDA
- cuDNN
- TensorFlow-gpu


### Check GPU
lspci | grep -i nvidia

### CUDA
https://developer.nvidia.com/cuda-toolkit
http://developer.download.nvidia.com/compute/cuda/repos/ubuntu1604/x86_64/

### cuDNN
https://developer.nvidia.com/rdp/cudnn-download
Create the account


### Path
#### CUDA and cuDNN paths
export PATH=/usr/local/cuda-8.0/bin:${PATH}
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64:${LD_LIBRARY_PATH}
