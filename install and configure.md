# Miniconda 的安装配置（Install and Configure）

## 一、Windows安装Miniconda

软件包下载地址：[Miniconda（官方）](https://repo.anaconda.com/miniconda/)、[Miniconda（清华镜像站）](https://mirrors.tuna.tsinghua.edu.cn/anaconda/miniconda/)

下载Windows版本当前最新的安装包，双击运行安装包进行安装。

1. 选择为所有用户安装，然后自定义合适安装的路径，安装时可直接添加相应路径至系统环境变量（测试是环境变量未成功添加）。
2. 选择为当前用户安装，然后自定义合适安装的路径，安装时可直接添加相应路径至系统环境变量。

## 二、配置系统环境变量

1. 在系统环境变量中添加Miniconda安装目录中的对应文件夹，如下图所示：

   ![1.env](E:/Note/Miniconda tutorials/img/1. env.png)

2. 其中前两项为Miniconda所需的环境变量：

   ![2. conda env](E:/Note/Miniconda tutorials/img/2. conda env.png)

3. 第一、三项为默认版本的Python所需的环境变量：

   ![3. python env](E:/Note/Miniconda tutorials/img/3. python env.png)

4. 分别在终端中运行以下命令测试配置是否成功：

   ```bash
   conda --version
   python --version
   pip --version
   ```

   

## 三、配置清华镜像源

1. 打开[清华开源软降镜像站中anaconda的使用帮助](https://mirrors.tuna.tsinghua.edu.cn/help/anaconda/)

2. Windows 用户先执行以下命令，在`C:\Users\<YourUserName>\.condarc`路径，创建名为 `.condarc` 的文件。

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
   pkgs_dirs:
     - D:\Environment\miniconda3\pkgs
   ```

2. 配置`miniconda3`文件夹的用户权限，给予`Users`用户完全控制权限，否则部分包由于权限不足无法安装。

## 五、PyPI配置清华镜像源

1. 在用户目录`C:\Users\<YourUserName>`中创建一个pip目录，如：`C:\Users\<YourUserName>\pip`，在pip文件夹中新建文件pip.ini，内容如下：

   ```bash
   [global]
   timeout = 6000
   index-url=https://pypi.tuna.tsinghua.edu.cn/simple/
   [install]
   trusted-host=mirrors.tsinghua.edu.cn
   ```

   *这里以清华源为例，其他常用*镜像源如下：*

   ```
   清华大学 ：https://pypi.tuna.tsinghua.edu.cn/simple
   中科大：https://pypi.mirrors.ustc.edu.cn/simple
   豆瓣：http://pypi.douban.com/simple
   阿里云 ：http://mirrors.aliyun.com/pypi/simple
   ```

2. 查看配置是否成功

   ```bash
   pip config list
   ```

3. 临时换源

   ```bash
   pip install package-name -i https://pypi.tuna.tsinghua.edu.cn/simple
   # 或
   pip install package-name -i https://pypi.tuna.tsinghua.edu.cn/simple --trusted-host pypi.tuna.tsinghua.edu.cn
   ```

   

   