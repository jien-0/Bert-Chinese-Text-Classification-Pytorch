# Bert-Chinese-Text-Classification-Pytorch
[![LICENSE](https://img.shields.io/badge/license-Anti%20996-blue.svg)](https://github.com/996icu/996.ICU/blob/master/LICENSE)

中文文本分类，Bert，ERNIE，基于pytorch，开箱即用。

## 介绍
模型介绍、数据流动过程：还没写完，写好之后再贴博客地址。  


## 环境
python 3.7  
pytorch 1.1  
tqdm  
sklearn  
tensorboardX  
[pytorch_pretrained_bert](https://github.com/huggingface/pytorch-transformers)  

## 中文数据集
我从[THUCNews](http://thuctc.thunlp.org/)中抽取了20万条新闻标题，已上传至github，文本长度在20到30之间。一共10个类别，每类2万条。数据以字为单位输入模型。

类别：财经、房产、股票、教育、科技、社会、时政、体育、游戏、娱乐。

数据集划分：

数据集|数据量
--|--
训练集|18万
验证集|1万
测试集|1万


### 更换自己的数据集
 - 按照我数据集的格式来格式化你的中文数据集。  


## 效果

模型|acc|备注
--|--|--
bert|94.04%|bert + fc  
ERNIE|92.75%|效果略差  

CNN、RNN、DPCNN、RCNN、RNN+Attention、FastText等模型效果，请见我另外一个[仓库](https://github.com/649453932/Chinese-Text-Classification-Pytorch)。  

## 预训练语言模型
bert模型放在 bert_pretain目录下，ERNIE模型放在ERNIE_pretrain目录下，每个目录下都是三个文件：
 - pytorch_model.bin  
 - bert_config.json  
 - vocab.txt  

预训练模型下载地址：  
bert_Chinese: https://s3.amazonaws.com/models.huggingface.co/bert/bert-base-chinese.tar.gz  来自[这里](https://github.com/huggingface/pytorch-transformers)  
ERNIE_Chinese: http://image.nghuyong.top/ERNIE.zip  来自[这里](https://github.com/nghuyong/ERNIE-Pytorch)  
解压后，按照上面说的放在对应目录下，文件名称确认无误即可。  

## 使用说明
下载好预训练模型就可以跑了。
```
# 训练并测试：
# bert
python run.py --model bert

# ERNIE
python run.py --model ERNIE
```

### 参数
模型都在models目录下，超参定义和模型定义在同一文件中。  

## 未完待续
 - bert + CNN, RNN, RCNN, DPCNN等  
 - ERNIE + CNN, RNN, RCNN, DPCNN等  
 - XLNET  
 - 另外想加个label smoothing试试效果  
 - 封装预测功能


## 对应论文
[1] BERT: Pre-training of Deep Bidirectional Transformers for Language Understanding  
[2] ERNIE: Enhanced Representation through Knowledge Integration  
