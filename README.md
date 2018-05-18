# mtcnn-caffe
Keras Implementation of Joint Face Detection and Alignment using Multi-task Cascaded Convolutional Neural Networks.
《基于多任务级联卷积神经网络的人脸检测和对齐》（论文名字）的Keras 实现；

This project provide you a method to update multi-task-loss for multi-input source.
这个工程提供给你一个针对多输入源更新多任务损失函数的方法
multi-task Convolutional Neural Network 多任务卷积神经网络；

Transplanted from MTCNN-caffe from CongweiLin's github repository
github.com/CongWeilin/mtcnn-caffe
从MTCNN-caffe，CongweiLin's github repository 移植过来；

# training requires Wider Face Training data set and CelebA data set (same as the caffe version).
训练需要widerface数据集和celeba数据集
However, the scripted is modified to reduce hard-disk usage. i.e. all intermediate cropped imgs are stored in memory.
但是，脚本被修改以减少硬盘的使用。也就是说，所有中间裁剪的imgs都存储在内存中。
Requires at least 16 Gb memory to precess training data.
至少需要16G 内存来处理数据；

# refined training process
完善（改进）训练过程
The refined training uses training strategy that closely follows the original caffe code. i.e. randomly select Classification loss,
roi regression loss or key point regression losses and minimize it for each batch of data. Slightly improve the performance.
But also makes the training code unnecessarrily complex.
Accuracy measurement is not implemented.
改进的训练使用的训练策略与最初的caffe代码密切相关。即随机选择分类损失、roi回归损失或关键点回归损失，并将每批数据最小化。稍微提高性能。但也使训练代码不必要地复杂。
精度测量没有实现。

gen_celebA_data_lmdb.py  对celeba 数据集做数据处理；
gen_net_data_lmdb.py     对widerface数据集做数据处理；
data_quality_confirmation.py  图片数据处理 确保数据质量；
training 文件夹    三个网络；第一级网络 多任务；
refine_training  改进训练网络；第二级网络 ；
MTCNN.py 第三级网络；
Run_model_caffe_weight.py  人脸识别；

utils.py ; tools_matrix.py; 工具类







