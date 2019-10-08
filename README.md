## Medium-SST

### Train and Test

```
# word-level
python run_SST.py --do_train --epoch_num=10   # train and test
python run_SST.py   # test

# char-level + word-level
python run_Highway_SST.py --do_train --epoch_num=10   # train and test
python run_Highway_SST.py  # test

tensorboard --logdir=.log   # 可视化分析
```

### Results

| model name            | acc    | F1    | loss  |
| --------------------- | ------ | ----- | ----- |
| TextCNN               | 92.53 | 92.5 | 0.195 |
| TextRNN               | 92.13 | 92.4 | 0.207 |
| LSTM_ATT              |   93.07     |  93.0    |  0.285     |
| TextRCNN | 94.06 | 94.0 | 0.165 |
| TextCNNHighway | 93.21 | 93.21 | 0.185 |
| TextRNNHighway | 92.03 | 92.03 | 0.199 |
| LSTMATTHighway | 93.02 | 93.01 | 0.278 |
| TextRCNNHighway | 93.266 | 93.37 | 0.167 |
### Analysis

由上表可以看出， 复杂模型要比简单模型表现好， 从 loss 曲线上看， 加上 `Highway Networks` 效果普遍会好，但并没有使得模型表现突飞猛进， 可能是由于SST数据集所用词汇相对简单的原因，OV问题并不严重 。







## Reference Papers

[1] TextCNN： Convolutional Neural Networks for Sentence Classification

[2] A Sensitivity Analysis of (and Practitioners' Guide to) Convolutional Neural Networks for Sentence Classification

[3] Recurrent Convolutional Neural Network for Text Classification

[4] Hierarchical Attention Networks for Document Classification

[5] Large Scale Multi-label Text Classification With Deep Learning
