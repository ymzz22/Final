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
"otsl":  # 保存OTSL相关标注
"html"  # 保存HTML相关标注
  "string": 原始HTML字符串
  "cells"：原始标注
  "tablemaster": TableMaster风格的标注
```

