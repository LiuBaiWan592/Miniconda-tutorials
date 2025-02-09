# Conda常用命令（Conda Common Commands）

## 一、管理conda

1. 查看conda版本

   ```bash
   conda --version
   conda -V
   ```

2. 列出所有的环境

    ```bash
    conda env list
    # conda info --envs
    ```

    *`conda list`命令用于查看conda下的包，而`conda env list`命令可以用来查看conda创建的所有虚拟环境。*

3. 查看环境管理的全部命令帮助

    ```bash
    conda env -h
    ```

## 二、管理环境

1. 创建环境

   ```bash
   # 在默认路径下创建环境，指定环境名为EnvName，Python版本为version，一同安装的包名为packages
   conda create --name EnvName python=version packages
   # conda create -n EnvName python=version packages -n等同于--name
   
   # 例如：
   conda create -n python3.8 python=3.8 pandas
   ```

   ```bash
   # 在指定路径下创建环境
   conda create --prefix EnvPath python=version packages
   # conda create -p EnvPath python=version packages -p等同于--prefix
   ```

2. 激活环境

   ```bash
   # 激活名为EnvName的环境
   conda activate EnvName
   # 激活路径为EnvPath的环境
   conda activate EnvPath
   
   # 激活默认，即base环境
   conda activate
   ```

3. 退出当前环境

   ```bash
   conda deactivate
   ```

4. 克隆环境

   ```bash
   # 通过克隆名为OldEnv的环境来创建一个称为NewEnv的副本
   conda create -n NewEnv --clone OldEnv
   ```

5. 删除环境

   ```bash
   # 删除名为EnvName的环境
   conda env remove -n EnvName
   # 删除路径为EnvPath的环境
   conda env remove -p EnvPath
   # 删除删除名为EnvName的环境及其安装包
   conda remove --name EnvName --all
   ```

6. 分享环境

   * 将当前名为EnvName的环境信息生成YAML文件。

     ```
     conda env export > EnvName.yaml
     ```

   * YAML文件格式：

     ```
     name: EnvName
     channels:
       - defaults
       - https://repo.anaconda.com/pkgs/main
       - https://repo.anaconda.com/pkgs/r
       - https://repo.anaconda.com/pkgs/msys2
     dependencies:
       - ca-certificates=2024.12.31=haa95532_0
       - libffi=3.4.4=hd77b12b_1
       - openssl=3.0.15=h827c3e9_0
       - pip=24.2=py38haa95532_0
       - python=3.8.20=h8205438_0
       - setuptools=75.1.0=py38haa95532_0
       - sqlite=3.45.3=h2bbff1b_0
       - vc=14.42=haa95532_3
       - vs2015_runtime=14.42.34433=he0abc0d_3
       - wheel=0.44.0=py38haa95532_0
     prefix: D:\Environment\miniconda3\envs\EnvName
     ```
	  
	* 利用YAML文件生成环境（可根据需要修改环境名和存放路径）
	
	  ```bash
	  conda env create -f EnvName.yaml
	  ```
	
	  

