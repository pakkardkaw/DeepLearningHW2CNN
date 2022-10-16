# HW 2: The pre-trained CNN, 3 Applications of image classification: KatokKatak

Simple overview of use/purpose.

## Data Source
1. Waste Images consist of xx,xxx images which can be catagorized into 4 groups
- Organic
- Recycle
- General
- Hazard
Source : ........

2. Hand writing Thai number data set cosist of xx,xxx images for 0-9 Thai digits
Source : 

3. Image of Budha posture for each day of week. Number of class is 8 as following
![image](https://user-images.githubusercontent.com/11289173/195136123-ef90c34c-7e1d-45cf-a181-8313a237b2b4.png)

Source : google search

An in-depth paragraph about your project and overview of use.

## Methodology
[Image of process flow]
0. set seed
 1111,2222,3333

1. Data Gathering and Labeling 
  1.1 Split data 60:20:20  Train Test validation
  1.2 
3. Image augmentation and standard preprocessing


| Dataset        | Rescale           | rotation            | zoom               |
|----------------|-------------------|---------------------|--------------------|
| Waste          | :heavy_check_mark:|:heavy_check_mark:   |:heavy_check_mark:  |
| Thai number    | :heavy_check_mark:|:heavy_check_mark:   |:heavy_check_mark:  |
| Image of budha | :heavy_check_mark:| :x:                 |:heavy_check_mark:  |

  2.1 rescale by divided by 255
  2.2 .....
  2.3 use standadard preprocessing for each model
4. Select 2 well-known CNN models, VGG16 and XXXXX with pre-trained imagenet result weight and remove classification layer set
  4.1 Select base model
    - VGG16 : Freeze all feature extraction layers
    - InceptionV3 : Freeze all feature extraction layers except last con2d layer,namely "conv2d_93"
  4.2 Added dense layers to perform clasification tasks
    - Image of Buddha :  
       - Dense512 relu -> dropout0.4-> Sense 128 relu -> dropout 0.4 -> Dense 64  Relu -> Dense 8  softmax
       - Optimizer = Adam
       - Loss function = categorical_crossentropy
       - Metric = Accuracy
   
8. Train Model
  6.1 Image of Buddha
   - Image size 256x256 px
   - batch size = 16
   - Epoch = 60
9. Evaluate model

### Result for each application

1. Waste Catagory Classification

3. Thai Digit Recognition

4. Image of Buddha Classification

# Base Model VGG16
Training Time :  417.45 seconds
Processor : RTX3060 TI RAM 8 GB

  | Seed | Dataset  | Records |   Lost   | Accuracy | Train Time (s) |
  |------|----------|---------|----------|----------|----------------|
  | 1111 | Train    |   1,112 |  0.3789  |  0.8516  |                |
  | 1111 | Validate |     368 |  1.0657  |  0.7391  |                |
  | 1111 | Test     |     372 |  0.9709  |  0.7419  |                |
  | 2222 | Train    |   1,112 |  0.3789  |  0.8516  |                |
  | 2222 | Validate |     368 |  1.0657  |  0.7391  |                |
  | 2222 | Test     |     372 |  0.9709  |  0.7419  |                |
  | 3333 | Train    |   1,112 |  0.3789  |  0.8516  |                |
  | 3333 | Validate |     368 |  1.0657  |  0.7391  |                |
  | 3333 | Test     |     372 |  0.9709  |  0.7419  |                |
  | avg  | Train    |   1,112 |  0.3789  |  0.8516  |                |
  | avg  | Validate |     368 |  1.0657  |  0.7391  |                |
  | avg  | Test     |     372 |  0.9709  |  0.7419  |                | 
  
![image](https://user-images.githubusercontent.com/11289173/195155214-3f374651-af6e-4c1c-91e3-176a1263a790.png)

![image](https://user-images.githubusercontent.com/11289173/195155232-19cda238-e3d6-49df-92de-379c36d9b439.png)


# Base Model InceptionV3
Training Time :   seconds
Processor : RTX3060 TI RAM 8 GB

  | Dataset  | Records |   Lost   | Accuracy |
  |----------|---------|----------|----------|
  | Train    |   1,112 |          |          |
  | Validate |     368 |          |          |
  | Test     |     372 |          |          |

### Comparison



## Team Members




## Acknowledgments

Inspiration, code snippets, etc.
* [Network Drawing tool](https://alexlenail.me/NN-SVG/AlexNet.html)
