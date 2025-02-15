# Pytorch安装配置教程

****

## 显卡驱动版本： 

**NVIDIA-SMI 560.94                 Driver Version: 560.94         CUDA Version: 12.6**

```bash
# 使用以下命令查看显卡驱动版本
nvidia-smi
```

## 环境安装版本：

**CUDA Toolkit: 11.8.0				python: 3.9   							pytorch: 2.2.2**

[Python、PyTorch与cuda的版本对应表 ](https://www.sdk.cn/details/Z253zkRaw5x78a0eAm)

## 一、下载安装CUDA Toolkit

1. 打开[CUDA Toolkit Archive | NVIDIA Developer](https://developer.nvidia.com/cuda-toolkit-archive)选择[CUDA Toolkit 11.8.0](https://developer.nvidia.com/cuda-11-8-0-download-archive)后，选择对应系统下载安装包

   ![pytorch 1. download cuda toolkit](img\pytorch 1. download cuda toolkit.png)

2. 下载完成后，双击运行进行安装。选择自定义安装只选择安装CUDA，并取消安装CUDA中的`Visual Studio Integration`

   ![pytorch 2. CUDA](img\pytorch 2. CUDA.png)

   ![pytorch 3. No VS](img\pytorch 3. No VS.png)
   
   3. 安装完后会在系统中添加以下环境变量
   
      ![pytorch 4. Environment](img\pytorch 4. Environment.png)
   
   4. 测试安装是否成功
   
      运行`nvcc -V`命令，出现以下版本号表示安装成功
   
      ![pytorch 5. nvcc -V](img\pytorch 5. nvcc -V.png)

## 二、创建pytorch虚拟环境

1. 打开`miniconda`创建`pytorch`的虚拟环境（[Python、PyTorch与cuda的版本对应表 ](https://www.sdk.cn/details/Z253zkRaw5x78a0eAm)）

   ```bash
   conda create -n pytorch2.2.2 python=3.9
   ```

2. 切换到`pytorch`虚拟环境准备安装

   ```bash
   conda activate pytorch2.2.2
   ```

## 三、安装pytorch到虚拟环境

1. 根据版本选择相应的安装命令（[Previous PyTorch Versions](https://pytorch.org/get-started/previous-versions/)）

   ```bash
   conda install pytorch==2.2.2 torchvision==0.17.2 torchaudio==2.2.2 pytorch-cuda=11.8 -c pytorch -c nvidia
   ```

2. 安装完成后测试是否安装成功

   ```bash
   # 虚拟环境下进入Python
   python
   # 依次运行以下命令
   import torch
   torch.cuda.is_available()
   ```

   运行结果为`True`则代表安装成功

   ![pytorch 6. Successful](img\pytorch 6. Successful.png)

   *导入`torch`时`numpy`报错，则适当降低`numpy`版本*
   
   ```
   conda install numpy=1.26
   ```
