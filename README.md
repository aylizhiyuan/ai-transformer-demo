## Transformer

### 0. 概念

人工智能最早的应用还是`自然语言处理(NLP)`和`图像识别(CNN)`

常见的自然语言处理任务(NLP)

- 情感分析: 对给定的文本分析其情感极性
- 文本生成: 根据给定的文本进行生成
- 命名实体识别: 标记句子中的实体
- 阅读理解: 给定上下文与问题,从上下文中抽取答案
- 掩码填充: 填充给定文本中的掩码词
- 文本摘要: 生成一段文本的摘要
- 机器翻译: 将文本翻译成另一种语言
- 特征提取: 生成给定文本的张量表示
- 对话机器人: 根据用户输入文本,产生回应,与用户对话

总而言之就是自然语言处理就是处理人类的语言

相关库介绍

- Transformers: 核心库
- Tokenizer: 分词器,数据进行预处理
- Datasets: 数据集,提供数据集的加载、处理
- Evaluate: 评估函数,提供各种评价指标的计算函数
- PEFT: 高效微调模型的库
- Accelerate: 分布式训练
- Optimum: 优化加速库
- Gradio: 可视化部署库






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

通常下载的模型需要自己手动进行清理,毕竟有些模型的大小确实非常的大

### 3. pipeline

- 将数据预处理、模型调用、结果后处理三部分组装成的流水线
- 使我们能够直接输入文本获得最终的答案


