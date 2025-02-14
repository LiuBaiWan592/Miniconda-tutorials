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