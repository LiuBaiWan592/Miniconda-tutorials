# Conda 中 Jupyter Notebook 的配置与使用

## 一、默认环境中安装和运行Jupyter Notebook

1. 安装完整Jupyter Notebook

   ```bash
   # 在默认Conda环境（base）中运行以下命令安装Jupyter Notebook
   conda install jupyter notebook
   # 或者
   conda install notebook
   ```

   **仅在默认Conda环境（base）中安装Jupyter Notebook即可，其他的虚拟环境只需要安装ipykernel即可进行切换**

2. 启动Jupyter Notebook

   ```bash
   # 在终端中任意路径下运行以下命令即可
   jupyter notebook
   ```

   **Jupyter Notebook在默认Conda环境（base）中安装后在Scripts路径下，该路径在配置Conda时已经添加进系统环境变量**

   **运行后自动打开浏览器，默认为8888端口，打开的目录即为执行上命令时终端中的路径，会在该路径下创建`.ipynb_checkpoints`目录，建议选择好合适的路径后在启动Jupyter Notebook**

## 二、添加其他环境至Jupyter Notebook

1. 安装`ipykernel`

   ```bash
   # 在要添加到Jupyter Notebook的虚拟环境中安装ipykernel，不需要安装完整的Jupyter Notebook
   conda install ipykernel
   ```

2. 将对应的虚拟环境添加至Jupyter Notebook

   ```bash
   # 在要添加至Jupyter Notebook的虚拟环境下执行以下命令
   python -m ipykernel install --user --name EnvName --display-name EnvName
   # 其中 EnvName 为要在Jupyter Notebook中创建的虚拟环境名，替换为当前Conda环境名即可
   # 例如：
   python -m ipykernel install --user --name base --display-name base
   python -m ipykernel install --user --name python3.8 --display-name python3.8
   ```

    **创建的Jupyter Notebook虚拟环境会存储在`C:\Users\UserName\AppData\Roaming\jupyter\kernels`目录下**