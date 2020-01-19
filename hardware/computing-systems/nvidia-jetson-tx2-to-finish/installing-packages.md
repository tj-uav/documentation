# Installing Packages

**Tensorflow-GPU**

Current tensorflow installation used [this forum](https://docs.nvidia.com/deeplearning/frameworks/install-tf-jetson-platform/index.html).

Grab dependencies and install tensorflow:

```text
python3 -m pip install -U numpy==1.16.1 future==0.17.1 mock==3.0.5 h5py==2.9.0 keras_preprocessing==1.0.5 keras_applications==1.0.8 gast==0.2.2 enum34 futures protobuf
python3 -m pip install --pre --extra-index-url https://developer.download.nvidia.com/compute/redist/jp/v43 tensorflow-gpu
```

**PyTorch**

Follow instructions on this forum: [https://devtalk.nvidia.com/default/topic/1049071/jetson-nano/pytorch-for-jetson-nano/](https://devtalk.nvidia.com/default/topic/1049071/jetson-nano/pytorch-for-jetson-nano/)

In case it gets taken down, the current commands are:

```text
wget https://nvidia.box.com/shared/static/ncgzus5o23uck9i5oth2n8n06k340l6k.whl -O torch-1.4.0-cp36-cp36m-linux_aarch64.whl
sudo apt-get install libopenblas-base
python3 -m pip install Cython
python3 -m pip install numpy torch-1.4.0-cp36-cp36m-linux_aarch64.whl
```

Test tensorflow and pyTorch in python terminal:

```text
import tensorflow
tf.test.is_gpu_available(cuda_only=False, min_cuda_compute_capability=None)
import torch
torch.cuda.is_available()
```



