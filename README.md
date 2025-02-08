# Miniconda tutorials

**Miniconda 的安装、配置和使用笔记教程**

## 一、Windows安装Miniconda

软件包下载地址：[Miniconda（官方）](https://repo.anaconda.com/miniconda/)、[Miniconda（清华镜像站）](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/)

下载Windows版本当前最新的安装包，双击运行安装包进行安装。

1. 选择为所有用户安装，然后自定义合适安装的路径，安装时可直接添加相应路径至系统环境变量（测试是环境变量未成功添加）。
2. 选择为当前用户安装，然后自定义合适安装的路径，安装时可直接添加相应路径至系统环境变量。

## 二、配置系统环境变量

1. 在系统环境变量中添加Miniconda安装目录中的对应文件夹，如下图所示：

   ![1.env](img/1. env.png)

2. 其中前两项为Miniconda所需的环境变量：

   ![2. conda env](img\2. conda env.png)

3. 第一、三项为默认版本的Python所需的环境变量

   ![3. python env](img\3. python env.png)

## 三、配置清华镜像源

1. 打开[清华开源软降镜像站中anaconda的使用帮助](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/)

2. Windows 用户先执行以下命令，在C:\Users\<YourUserName>\.condarc路径，创建名为 `.condarc` 的文件。

   ```bash
   conda config --set show_channel_urls yes
   ```

   

3. 复制镜像站中的配置信息替换掉`.condarc`中的内容，镜像站中的配置信息如下：

   ```
   channels:
     - defaults
   show_channel_urls: true
   default_channels:
     - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/main
     - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/r
     - https://mirrors.tuna.tsinghua.edu.cn/anaconda/pkgs/msys2
   custom_channels:
     conda-forge: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
     pytorch: https://mirrors.tuna.tsinghua.edu.cn/anaconda/cloud
   ```

4. 执行以下命令查看是否更改成功：

   ```bash
   conda config --show
   ```

## 四、修改默认虚拟环境安装位置

1. 再次打开`.condarc`文件，在最后添加以下语句，并保存。

   ```
   envs_dirs:
     - D:\Environment\miniconda3\envs
   ```

2. 配置`envs`文件夹的用户权限，给予`Users`用户完全控制权限。