# Installing Packages

**Tensorflow-GPU**

**PyTorch**

Follow instructions on this forum: [https://devtalk.nvidia.com/default/topic/1049071/jetson-nano/pytorch-for-jetson-nano/](https://devtalk.nvidia.com/default/topic/1049071/jetson-nano/pytorch-for-jetson-nano/)

In case it gets taken down, the current commands are:

```text
wget https://nvidia.box.com/shared/static/ncgzus5o23uck9i5oth2n8n06k340l6k.whl -O torch-1.4.0-cp36-cp36m-linux_aarch64.whl
sudo apt-get install libopenblas-base
python3 -m pip install Cython
python3 -m pip install numpy torch-1.4.0-cp36-cp36m-linux_aarch64.whl
```



