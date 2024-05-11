## Transformer

### 0. 概念

### 1. 创建和使用虚拟环境

首先确保自己安装了`python3`,安装方式其实很多,这里就不叙述了

创建自己的项目文件夹`my_product`,转到项目目录中运行以下命令,将会在本地文件夹下创建一个新的虚拟环境`.venv`

```
// 可将这个文件忽略,应该安装的软件包都在这个里面
python3 -m venv .venv
```

然后激活这个虚拟环境

```
source .venv/bin/activate
// 查看python的虚拟环境是否激活
which python3
// 停用这个虚拟环境,或者直接关闭shell,如果关闭请重新激活它
deactivate
```

升级`pip`,pip 是 Python 的包管理器,它用于将软件包安装和更新到虚拟环境中

```
python3 -m pip install --upgrade pip
python3 -m pip --version
```

安装软件包

```
// 安装软件包
python3 -m pip install requests
// 安装特定版本的软件包
python3 -m pip install 'requests==2.18.4'
// 安装最新的2.x版本的软件包
python3 -m pip install 'requests>=2.0.0,<3.0.0'
// 升级包
python3 -m pip install --upgrade requests
// 根据需求文件进行安装,例如创建一个requirements.txt并包含以下文件
requests==2.18.4
google-auth==1.1.0
// 告诉pip根据文件进行安装
python3 -m pip install -r requirement.txt
```

可使用以下命令导出所有安装的软件包及其版本的列表

```
python3 -m pip freeze
```

### 2. 安装 TensorFlow / PyTorch

```
python3 -m pip install tensorflow
python3 -m pip install torch torchvision torchaudio

python3 -m pip install transformers
```
