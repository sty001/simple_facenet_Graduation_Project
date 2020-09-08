# understand_facenet
### 最适合初学者的facenet入门程序：

主要是整理和注释了facenet的代码，以便初学者更好地理解facenet的代码。


这里还有一篇解读代码的博客和详细代码使用指南：【史上最全的FaceNet源码使用方法和讲解】http://blog.csdn.net/u013044310/article/details/79556099 结合本文章，疗效更佳。

一star一鼓励，如果觉得有用，麻烦给个星星给我动力。

声明：本代码只用于学习以及入门facenet用，具体请看原始代码，源代码地址：https://github.com/davidsandberg/facenet

python3 align/align_dataset_mtcnn.py ../../Datasets/lfw_funneled ../../Datasets/lfw_mtcnnpy_160x160 --image_size 160 --margin 32 --random_order

python3 validate_on_lfw.py ../../Datasets/lfw_mtcnnpy_160x160 ./models/20170512-110547
The best threshold is 1.19
The best threshold is 1.22
The best threshold is 1.22
The best threshold is 1.19
The best threshold is 1.19
The best threshold is 1.29
The best threshold is 1.22
The best threshold is 1.22
The best threshold is 1.22
The best threshold is 1.22
Accuracy: 0.992+-0.004
Validation rate: 0.97200+-0.01740 @ FAR=0.00133
Area Under Curve (AUC): 1.000
Equal Error Rate (EER): 0.007

python3 compare.py ./models/20170512-110547 ./data/1.png ./data/2.png
Distance matrix
        0         1
0    0.0000    1.3609
1    1.3609    0.0000

python3 compare.py ./models/20170512-110547 ./data/inesta.jpg ./data/messi.jpg
Distance matrix
        0         1
0    0.0000    1.5232
1    1.5232    0.0000

python3 compare.py ./models/20170512-110547 ./data/jobs2.jpg ./data/jobs3.jpg
Distance matrix
        0         1
0    0.0000    0.9006
1    0.9006    0.0000

自行crop至150*150：
true mean 0.713366
false mean 1.38062
best threshold 1.11
test accuracy 0.9815

facenet在MTCNN进行crop：
true mean 0.671977
false mean 1.39559
best threshold 1.11
test accuracy 0.993167

dlib在用MTCNN进行crop：
true mean 0.451932
false mean 0.795374
best threshold 0.61
test accuracy 0.964

