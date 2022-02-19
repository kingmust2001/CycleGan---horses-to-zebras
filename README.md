# CycleGan---horses-to-zebras

## 專案介紹
CycleGAN is another application of Generative Adversarial Network (GAN) which could handle image-to-image translation problem.

The goal of image to image translation is to learn mapping between input and output image. 

In this case, we could apply CycleGAN method to transfer the feature of zebras  image to horses image.

## 軟硬體配置
* CPU: Intel(R) Xeon(R) (6-cores)
* GPU: Tesla K80 (11.44GB)
* OS： Window10
* Pytorch: 1.10.0
* keras: 2.7.0
* tensorflow: 2.7.0
* Memory: 12.69GB
## 資料來源
tensorflow dataset horses to zebra

https://www.tensorflow.org/datasets/catalog/cycle_gan#cycle_ganhorse2zebra

![image](https://user-images.githubusercontent.com/77257138/154804374-c4782872-d916-4d3f-80dd-afa0308d37b6.png)

## 資料基本資訊
training set: 1067 

testing set: 120

## 前處理
* random flip
* random crop
* resize
## 模型

![image](https://user-images.githubusercontent.com/77257138/154804007-e7f4a8c9-afde-43be-a95d-40a254201720.png)

![image](https://user-images.githubusercontent.com/77257138/154804412-4f1c50c6-3f80-4c2e-8530-48d49b2dbb75.png)

![image](https://user-images.githubusercontent.com/77257138/154804418-6863168e-5dad-4ce6-8304-e9235827f61c.png)

## Metrics
Mean absolute error on cycle network and discriminator(MAE)

## 成果
epoch:1

generator_horses_loss: 3.9191 - generator_zebras_loss: 3.7237 - Discriminator_horses_loss: 0.1992 - Discriminator_zebras_loss: 0.2023

![image](https://user-images.githubusercontent.com/77257138/154804458-2624e0e3-d530-4a7d-a32a-0f7296e15b79.png)

## Reference
https://arxiv.org/pdf/1703.10593.pdf
https://github.com/junyanz/pytorch-CycleGAN-and-pix2pix
https://keras.io/examples/generative/cyclegan/
https://ithelp.ithome.com.tw/articles/10244859
https://www.rs-online.com/designspark/jetson-nanogoogle-colabcyclegan-2-cn

## other
 1. instead of using batchNormalization(BN), InstanceNormalization(IN) could consider each image feature.
 
![image](https://user-images.githubusercontent.com/77257138/154804830-289a8ec1-2d5e-4acc-9b06-6a4b11e24057.png)

2. Residual Block to solve vanishing gradient and exploding gradient problem. Residual Block are skip-connection blocks that learn residual functions with reference to the layer inputs, instead of learning unreferenced functions. They were introduced as part of the ResNet architecture. (https://paperswithcode.com/method/residual-block)

![image](https://user-images.githubusercontent.com/77257138/154805042-07dd7e91-c038-4b95-9323-c6f499ea6c09.png)

3. Reflection padding - Pads the input tensor using the reflection of the input boundary. to keep the feature of image.

![image](https://user-images.githubusercontent.com/77257138/154805198-ce77aec8-c467-427d-a185-65b966402f9d.png)

