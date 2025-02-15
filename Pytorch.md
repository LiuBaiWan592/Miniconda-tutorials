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
