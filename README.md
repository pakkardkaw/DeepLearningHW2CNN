# HW 2: The pre-trained CNN, 3 Applications of image classification: KatokKatak
![image](https://user-images.githubusercontent.com/11289173/195136123-ef90c34c-7e1d-45cf-a181-8313a237b2b4.png)

Simple overview of use/purpose.

## Data Source
Collect image from google search 1,852 picture of image of budha for each day and split data using systematic ramdom using ranking of file name.

|  Class  |   Train  |  Validate  |  Test  |
|         |     60%  |      20%   |   20%  |
|---------|----------|------------|--------|
| Mon     |     115  |      37    |   39   |
| Tue     |     113  |      37    |   39   |
| Wed (m) |     112  |      38    |   39   |
| Wed (n) |     112  |      39    |   38   |
| Thu     |     125  |      42    |   40   |
| Fri     |     202  |      69    |   68   |
| Sat     |     157  |      51    |   54   |
| Sun     |     184  |      63    |   63   |


Source : see reference.xls

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
| Image of budha | :heavy_check_mark:| :x:                 |:heavy_check_mark:  |

  2.1 rescale by divided by 255
  2.2 .....
  2.3 use standadard preprocessing for each model
4. Select 2 well-known CNN models, VGG16 and XXXXX with pre-trained imagenet result weight and remove classification layer set
  4.1 Select base model
    - VGG16 : Freeze all feature extraction layers
    - InceptionV3 : Freeze all feature extraction layers except last con2d layer,namely "conv2d_93"
  4.2 Added dense layers to perform clasification tasks
    - Modified VGG16 :  
       - Dense512 relu -> dropout0.4-> Sense 128 relu -> dropout 0.4 -> Dense 64  Relu -> Dense 8  softmax
       - Optimizer = Adam
       - Loss function = categorical_crossentropy
       - Metric = Accuracy
![image](https://user-images.githubusercontent.com/11289173/196020339-00d0b629-ec92-4a18-ab36-70e4124f1ea4.png)


       
   
8. Train Model
  6.1 Image of Buddha
   - Image size 256x256 px
   - batch size = 16
   - Epoch = 60
9. Evaluate model

### Result for each Model

# Base Model VGG16
Processor : Tesla T4

  |  Model | Dataset  | Records |   Lost   | Accuracy | Train Time (s) |
  |--------|----------|---------|----------|----------|----------------|
  | VGG16  | Train |     368 |0.3363±0.04|0.8735±0.01          |     1018.8567±7.955           |
  | VGG16  | Validate     |     372 |1.1404±0.06|0.7446±0.01          |                | 
  | VGG16  | test    |   1,112 |1.2113±0.15|0.7301±0.01          |                |
  


### Comparison



## Team Members




## Acknowledgments

Inspiration, code snippets, etc.
* [Network Drawing tool](https://alexlenail.me/NN-SVG/AlexNet.html)
