## Tensorflow on GPU
https://www.tensorflow.org/install/install_linux
1. CUDA
1. cuDNN
1. TensorFlow-gpu

```
sudo apt-get install cuda-command-line-tools
```

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


```bash:.bash_profile
export PATH=/usr/local/cuda-8.0/bin:${PATH}  
export LD_LIBRARY_PATH=/usr/local/cuda-8.0/lib64:${LD_LIBRARY_PATH}
#export LD_LIBRARY_PATH=${LD_LIBRARY_PATH:+${LD_LIBRARY_PATH}:}/usr/local/cuda/extras/CUPTI/lib64
```

## Using GPU
https://www.tensorflow.org/programmers_guide/using_gpu
```python:gpu_test.py
# Creates a graph.
a = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[2, 3], name='a')
b = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[3, 2], name='b')
c = tf.matmul(a, b)
# Creates a session with log_device_placement set to True.
sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))
# Runs the op.
print(sess.run(c))
```

```python:gpu_test.py
# Creates a graph.
with tf.device('/cpu:0'):
  a = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[2, 3], name='a')
  b = tf.constant([1.0, 2.0, 3.0, 4.0, 5.0, 6.0], shape=[3, 2], name='b')
c = tf.matmul(a, b)
# Creates a session with log_device_placement set to True.
sess = tf.Session(config=tf.ConfigProto(log_device_placement=True))
# Runs the op.
print(sess.run(c))
```
