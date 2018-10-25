
#### 谷歌官方
1. [Introduction](https://www.tensorflow.org/serving/ )
2. [Building Standard TensorFlow ModelServer](https://www.tensorflow.org/serving/serving_advanced )
2. [Serving Inception Model with TensorFlow Serving and Kubernetes](https://www.tensorflow.org/serving/serving_inception )
3. [Serving a TensorFlow Model](https://www.tensorflow.org/serving/serving_basic )

#### 外部教程

1. [TensorFlow机器学习模型快速部署指南](https://www.jiqizhixin.com/articles/tensorflow-simple-ml-serving )
2. [上文的原版，Simple step-by-step guide to deploying deep learning models to production](https://github.com/hiveml/simple-ml-serving )
2. [如何使用Keras、Redis、Flask和Apache把深度学习模型部署到生产环境？](https://www.jiqizhixin.com/articles/2018-02-12 )
3. [How to deploy Machine Learning models with TensorFlow. Part 1 — make your model ready for serving](https://towardsdatascience.com/how-to-deploy-machine-learning-models-with-tensorflow-part-1-make-your-model-ready-for-serving-776a14ec3198 )
4. [How to deploy Machine Learning models with TensorFlow. Part 2— containerize it!](https://towardsdatascience.com/how-to-deploy-machine-learning-models-with-tensorflow-part-2-containerize-it-db0ad7ca35a7 )
4. [How to deploy Machine Learning models with TensorFlow. Part 3— into the Cloud!](https://towardsdatascience.com/how-to-deploy-machine-learning-models-with-tensorflow-part-3-into-the-cloud-7115ff774bb6 )
5. [TensorFlow Serving client. Make it slimmer and faster!](https://towardsdatascience.com/tensorflow-serving-client-make-it-slimmer-and-faster-b3e5f71208fb )
5. [TensorFlow Serving 101 pt. 1](https://medium.com/epigramai/tensorflow-serving-101-pt-1-a79726f7c103 )
6. [TensorFlow Serving 101 pt. 2](https://medium.com/epigramai/tensorflow-serving-101-pt-2-682eaf7469e7 )
7. [tensorflow model server 回归模型保存与调用方法](https://blog.csdn.net/u011961856/article/details/79686938 )
8. [Deployment of TensorFlow models into production with TensorFlow Serving](https://github.com/Vetal1977/tf_serving_example )

#### 将keras转成serving
1. [Serving Keras Models With Tensorflow Serving
](https://stackoverflow.com/questions/43649591/serving-keras-models-with-tensorflow-serving?utm_medium=organic&utm_source=google_rich_qa&utm_campaign=google_rich_qa )
2. [Tensorflow serving Keras model](https://github.com/tensorflow/serving/issues/310 )
3. [Exporting deep learning models from keras to tensorflow-serving](https://medium.com/@mr.acle/exporting-deep-learning-models-from-keras-to-tensorflow-serving-7d4a6e49ce3 )


#### 安装步骤

1. sudo apt-get update && sudo apt-get install -y \
        build-essential \
        curl \
        libcurl3-dev \
        git \
        libfreetype6-dev \
        libpng12-dev \
        libzmq3-dev \
        pkg-config \
        python-dev \
        python-numpy \
        python-pip \
        software-properties-common \
        swig \
        zip \
        zlib1g-dev
2. pip install 'tensorflow-serving-api-python3~=1.6.0' [官方不支持py3，参考](https://github.com/tensorflow/serving/issues/700 )
3. sudo apt-get update && sudo apt-get install tensorflow-model-server
3. [libstdc++.so.6: version `GLIBCXX3.4.22' not found](https://blog.csdn.net/u011961856/article/details/79644342 )
4. [提示`libstdc++.so.6: version `CXXABI_1.3.11'](https://github.com/shadowsocks/shadowsocks-qt5/issues/614 )
5. python model1_saved_model.py
4. tensorflow_model_server --port=9000 --model_name=model1 --model_base_path=/mnt/ai_check/1805_ModelAsServer/model1_0324_v2/export
6. python model1_client.py --server 106.12.20.59:9000 --image test_img/7.jpg