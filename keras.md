
#### 使用技巧

1. [如何让keras支持GPU](https://anaconda.org/anaconda/keras-gpu )
2. [将merge层改成Add/Multiply](https://stackoverflow.com/questions/42823627/how-to-use-merge-layer-concat-function-on-keras-2-0-0/42827064?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa )
3. [查看keras是否支持GPU](https://stackoverflow.com/questions/45662253/can-i-run-keras-model-on-gpu )
4. [keras导入模型后无法定义ctc损失](https://github.com/keras-team/keras/issues/5916 )
    ```
    model.compile(loss={'ctc': lambda y_true, y_pred: y_pred}, optimizer=sgd, metrics=['accuracy'])
    when load_model('model.hdf5', custom_objects={'ctc': lambda y_true, y_pred: y_pred})
    it raise "Unknown loss function: ''
    I was able to use custom_objects = {'<lambda>': lambda y_true, y_pred: y_pred} as a work-around.
    ```
    ```
    model = load_model('model/multi_task/try.h5', custom_objects={'loss_max': loss_max})
    my loss function:

    def loss_max(y_true, y_pred):
    from keras import backend as K
    return K.max(K.abs(y_pred - y_true), axis=-1)
    ```
6. [Keras as a simplified interface to TensorFlow: tutorial](https://blog.keras.io/keras-as-a-simplified-interface-to-tensorflow-tutorial.html )
7. [在keras中使用tensorflow的dataset接口](https://github.com/keras-team/keras/blob/master/examples/mnist_dataset_api.py )
11. [keras指定运行时显卡及限制GPU用量](https://blog.csdn.net/A632189007/article/details/77978058 )
12. [keras深度训练4:GPU设置，写的很详细](https://blog.csdn.net/github_36326955/article/details/79910448 )
12. [保存Tokenizer](https://stackoverflow.com/questions/45735070/keras-text-preprocessing-saving-tokenizer-object-to-file-for-scoring/45737582 )
```
    import pickle

    # saving
    with open('tokenizer.pickle', 'wb') as handle:
        pickle.dump(tokenizer, handle, protocol=pickle.HIGHEST_PROTOCOL)

    # loading
    with open('tokenizer.pickle', 'rb') as handle:
        tokenizer = pickle.load(handle)
```
13. [resume training from previous epoch #1872](https://github.com/keras-team/keras/issues/1872 )
14. [Online Learning in Keras? #1868](https://github.com/keras-team/keras/issues/1868 )
15. [解决keras/tensorflow由于cudnn版本较低，启动速度慢的问题](https://anaconda.org/anaconda/cudatoolkit )
16. [Keras error “You must feed a value for placeholder tensor 'bidirectional_1/keras_learning_phase' with dtype bool”](https://stackoverflow.com/questions/42969779/keras-error-you-must-feed-a-value-for-placeholder-tensor-bidirectional-1-keras )
17. [How to export Keras .h5 to tensorflow .pb?](https://stackoverflow.com/questions/45466020/how-to-export-keras-h5-to-tensorflow-pb )
18. [TensorFlow: How to freeze a model and serve it with a python API](https://blog.metaflow.fr/tensorflow-how-to-freeze-a-model-and-serve-it-with-a-python-api-d4f3596b3adc )
19. [通过并行加速fit_generator](https://keunwoochoi.wordpress.com/2017/08/24/tip-fit_generator-in-keras-how-to-parallelise-correctly/ )
20. [使用ImageDataGenerator后如何获知各个类别及对应的序号](https://stackoverflow.com/questions/48373685/keras-imagedatagenerator-how-to-get-all-labels-from-data )
21. [how to use fit_generator with multiple image inputs #8130](https://github.com/keras-team/keras/issues/8130 )


#### LSTM
1. [Understand the Difference Between Return Sequences and Return States for LSTMs in Keras](https://machinelearningmastery.com/return-sequences-and-return-states-for-lstms-in-keras/ )
2. [理解LSTM在keras API中参数return_sequences和return_state](https://blog.csdn.net/u011327333/article/details/78501054 )
3. [LSTM — nuggets for practical applications](https://towardsdatascience.com/lstm-nuggets-for-practical-applications-5beef5252092 )
4. [How to predict Bitcoin and Ethereum price with RNN-LSTM in Keras](https://medium.com/@siavash_37715/how-to-predict-bitcoin-and-ethereum-price-with-rnn-lstm-in-keras-a6d8ee8a5109 )
5. [Predicting Cryptocurrency Prices With Deep Learning](https://dashee87.github.io/deep%20learning/python/predicting-cryptocurrency-prices-with-deep-learning/ )
6. [A Guide For Time Series Prediction Using Recurrent Neural Networks (LSTMs)](https://blog.statsbot.co/time-series-prediction-using-recurrent-neural-networks-lstms-807fa6ca7f )
7. [【干货】RNN-LSTM的Keras实现：以预测比特币和以太坊价格为例（附代码））](https://mp.weixin.qq.com/s?__biz=MzU2OTA0NzE2NA==&mid=2247489374&idx=1&sn=f447719f13e2e7ac2deb2902c3827f2f&chksm=fc85f64dcbf27f5b1fb6decb7ea2f5b78236db4dcbf5faaecc3d9aa41e6bc5b8ff2bda90464b&mpshare=1 )
8. [涨姿势！用深度学习LSTM炒股：对冲基金案例分析](https://mp.weixin.qq.com/s?__biz=MjM5MTQzNzU2NA==&mid=2651658748&idx=1&sn=573b386b7697e44ac88043dd34403818&chksm=bd4c3e6f8a3bb779184fcf1da9589e57707aefe39c863be2881b051e3405823f71ba0e71d69f&mpshare=1 )
9. [【深入研究】使用RNN预测股票价格系列一](https://mp.weixin.qq.com/s?__biz=MzAxNTc0Mjg0Mg==&mid=2653286558&idx=1&sn=25441578341bde783cf8190e877c55f1&chksm=802e328bb759bb9d28e420d783a61944adc1369c6371962d5ba55d7de13df1272ef7232313ec&mpshare=1 )

#### CTC相关
1. [keras的ctc例子](https://github.com/keras-team/keras/blob/master/examples/image_ocr.py )
6. [基于keras的RNN英文字母识别，有助于理解上文](http://chongdata.com/articles/?p=819 )
5. [使用 Keras 来破解 captcha 验证码](https://ypw.io/captcha/ )
6. [上文的开源库](https://github.com/ypwhs/baiduyun_deeplearning_competition#%E5%9B%9B%E5%88%99%E6%B7%B7%E5%90%88%E8%BF%90%E7%AE%97%E8%AF%86%E5%88%AB%E5%86%B3%E8%B5%9B )
18. [A Keras CTC implementation of Baidu's DeepSpeech for model experimentation](https://github.com/robmsmt/KerasDeepSpeech )
13. [DeepSpeech, Speech To Text, ASR, Speech recognition, Keras, Tensorflow](https://github.com/ShankHarinath/DeepSpeech2-Keras )
4. [基于Tensorflow和Keras实现端到端的不定长中文字符检测和识别](https://github.com/YCG09/chinese_ocr )


#### OCR相关
1. [使用腾讯云 GPU 学习深度学习系列之五：文字的识别与定位](https://cloud.tencent.com/developer/article/1005199 )
9. [Keras GRU 文字识别](https://blog.csdn.net/dcrmg/article/details/79306402 )
10. [用keras实现OCR定位、识别](https://github.com/xiaomaxiao/keras_ocr )


#### seq2seq
1. [十分钟搞定Keras序列到序列学习（附代码实现）](https://www.jiqizhixin.com/articles/2017-10-03-2 )
2. [上文的原版](https://blog.keras.io/a-ten-minute-introduction-to-sequence-to-sequence-learning-in-keras.html )
3. [Neural Machine Translation — Using seq2seq with Keras](https://towardsdatascience.com/neural-machine-translation-using-seq2seq-with-keras-c23540453c74 )
4. [Sequence to Sequence Learning with Keras](https://github.com/farizrahman4u/seq2seq )
5. [seq2seq 的 keras 实现](https://blog.csdn.net/aliceyangxi1987/article/details/73420283 )
6. [keras系列︱seq2seq系列相关实现与案例（feedback、peek、attention类型）](https://blog.csdn.net/sinat_26917383/article/details/75050225 )
7. [A ten-minute introduction to sequence-to-sequence learning in Keras](https://blog.keras.io/a-ten-minute-introduction-to-sequence-to-sequence-learning-in-keras.html )

#### 多标签和多分类
1. [手把手教你用Keras进行多标签分类](https://zhuanlan.zhihu.com/p/39996321?utm_source=ZHShareTargetIDMore&utm_medium=social&utm_oi=28954110984192 )
2. [上文的英文原文](https://www.pyimagesearch.com/2018/05/07/multi-label-classification-with-keras/ )
2. [教程 | 使用Keras实现多输出分类：用单个模型同时执行两个独立分类任务](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2650747013&idx=3&sn=db30f433e3241cfdf696dc2466c2f772&chksm=871af4fbb06d7ded75430b0793573e8016b61efa012de5e1638e5b2345760d796c1a1b996996 )


#### 部署
1. [Building a simple Keras + deep learning REST API](https://blog.keras.io/building-a-simple-keras-deep-learning-rest-api.html )


#### 自动建模
1. [NAS框架AUTO Keras帮你搜索最佳深度模型](https://mp.weixin.qq.com/s?__biz=MzU2OTA0NzE2NA==&mid=2247494035&idx=1&sn=7f7e9c2b7b7f72b07634527e816e973c&chksm=fc860880cbf18196e9bc683420261b1ffe20784ae2ad4e07ae92d88330a3847d1dff70ae9cf1 )
2. [终结谷歌每小时20美元的AutoML！开源的AutoKeras了解下x](https://mp.weixin.qq.com/s?__biz=MzA3MzI4MjgzMw==&mid=2650746468&idx=1&sn=a71bae56bc19b0996666441c1087371b&chksm=871aea1ab06d630c73eef72e3a08c2737e64c4d20b8d1be9605e1740acf782458a5160c9baea&mpshare=1 )

#### estimator
1. [An Easy Guide to build new TensorFlow Datasets and Estimator with Keras Model](https://www.dlology.com/blog/an-easy-guide-to-build-new-tensorflow-datasets-and-estimator-with-keras-model/ )