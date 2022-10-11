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
    - VGG16
    - XXXX
  4.2 Added dense layers to perform clasification tasks
    - Image of Buddha :  
       - Dense512 relu -> dropout0.5-> Sense 64 relu -> dropout 0.5 -> Dense 32  Relu -> Dense 8  softmax
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
Training Time :  423 seconds
Processor : RTX3060 TI RAM 8 GB

  | Dataset  | Records |   Lost   | Accuracy |
  |----------|---------|----------|----------|
  | Train    |   1,112 |  0.6178  |  0.7590  |
  | Validate |     368 |  1.0016  |  0.7283  |
  | Test     |     372 |  1.0368  |  0.6882  |
  
![image](https://user-images.githubusercontent.com/11289173/195145837-adb87c46-a877-4435-b1be-b77645768871.png)
![image](https://user-images.githubusercontent.com/11289173/195145861-b8daeaab-0e47-4cd5-b38b-1e2bf205d839.png)




### Comparison



## Team Members




## Acknowledgments

Inspiration, code snippets, etc.
* [Network Drawing tool](https://alexlenail.me/NN-SVG/AlexNet.html)
