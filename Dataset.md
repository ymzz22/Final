# 数据集

使用PubTabNet和FinTabNet这两个数据集。

## 存储格式

以LMDB格式存储

```python
- image_db  # 保存图像
- ann_train_db  # 保存训练标注
- ann_test_db  # 保存测试标注
```
keys保持一致，均为去除后缀的文件名，如'PMC1064074_007_00'。

图像使用ImageDatabase类处理，标注使用Database类处理。

## 标注格式

```python

"filename": PMC1064074_007_00
"imgid": 351584
"html_string"： 原始HTML字符串
"ann_1": # 类型1
  "cells": 原始风格的标注
  "otsl": OTSL相关标注
  "tablemaster": TableMaster风格的标注
"ann_2": # 类型2
"ann_3": # 类型3
"ann_4": # 类型4

```

## 标注类型

按照空单元格、BBox标注类型分类：

- 类型#1：有空单元格标注、Bbox tight
- 类型#2：无空单元格标注、Bbox tight
- 类型#3：有空单元格标注、Bbox Padded
- 类型#4：无空单元格标注、Bbox Padded
