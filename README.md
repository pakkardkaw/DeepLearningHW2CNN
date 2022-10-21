<p align="center">
  <img width="660" height="360" src="https://user-images.githubusercontent.com/11289173/196726512-f1994677-141e-4d24-bdbe-887146d323b5.jpg">
</p>

# Buddha Posture Images classification using pre-trained CNN models

## <img src="https://user-images.githubusercontent.com/101813544/197007851-a8f8f95c-a853-41f4-8b67-0226e21a5b2d.png" width="36" height="36">  Highlights
* This project aims to perform multi-class classification on a total of 8 classes of Buddha posture images dataset and compare performance between the pre-trained model and after-fine tuned model using total 5 CNN models (VGG16, EfficientNetB0, ResNet50, MobileNetV2, and InceptionResNetV2)  
* Pre-trained accuracy results range from 61% to 73%. Loss values range from 0.75 to 1.20. The best model with lowest loss value and highest accuracy score is EfficientNetB0.
* After tuning accuracy results range from 67% to 82%. Loss values range from 0.72 to 1.08. The best model with lowest loss value and highest accuracy score is InceptionResNetV2 with 34% accuracy score improvement.

## <img src="https://user-images.githubusercontent.com/101813544/197007851-a8f8f95c-a853-41f4-8b67-0226e21a5b2d.png" width="36" height="36"> Contents
* Introduction
* Data
  - Data Source
* Methodology
  - Data Preprocessing/ Augmentation
  - CNN Models
  - Fine Tuning Models
* Results
* Discussion and Conclusion

## <img src="https://user-images.githubusercontent.com/101813544/197008423-3f4f5b4a-0481-4e63-8448-2d3b9ac32a22.png" width="40" height="40"> 1). Introduction: Multi-Class Classification
* This project aims to use transfer learning on a pre-trained CNN to perform multi-class classification on postures of Buddha images dataset and compare the pre-trained model and after-fine tuned model performances.  
* A pre-trained model is a network that's already been trained on a large dataset and saved, which can be adapted efficiently to our custom dataset. 
* Total 5 pre-trained models will be used in this project (VGG16, EfficientNetB0, ResNet50, MobileNetV2, and InceptionResNetV2). These models have been pre-trained on ImageNet, a dataset containing over 14 million images and 1,000 classes.

## <img src="https://user-images.githubusercontent.com/101813544/197008423-3f4f5b4a-0481-4e63-8448-2d3b9ac32a22.png" width="40" height="40"> 2). Data
* Data Source:
  - This dataset contains a total of 1,852 Buddha Posture images representing each day in a week, which were collected from Google search and systematically random split using ranking of file name.

<p align="center">
  <img width="750" height="400" src="https://user-images.githubusercontent.com/88955224/196983505-08f8eace-b231-47e0-bd84-06e2f484d401.png">
</p>

  - Total 8 classes were labeled: 0 Monday, 1 Tuesday, 2 Wednesday, 3 Wednesday_Night, 4 Thursday, 5 Friday, 6 Saturday, and 7 Sunday
  - Data Reference: For more information about the dataset, refer to Sources (see [reference.xlsx](reference.xlsx)).

## <img src="https://user-images.githubusercontent.com/101813544/197008423-3f4f5b4a-0481-4e63-8448-2d3b9ac32a22.png" width="40" height="40"> 3). Methodology

  <img src="https://user-images.githubusercontent.com/101813544/197014329-344cd70c-2094-46bb-9e47-6e2e605ef891.png" width="34" height="34"> 3.1). Data Gathering and Splitting:
  * Create the Dataset and Split it into Training, Validation, and Test datasets (60:20:20) with a systematic random method using class and file name as sorting key.
  * Now let's look at some of the images from the training set:

<p align="center">
  <img width="800" height="360" src="https://user-images.githubusercontent.com/88955224/196984880-0f2f0591-395b-4499-98cd-06a9df4083d0.png">
</p>

<p align="center">
  <img width="400" height="550" src="https://user-images.githubusercontent.com/88955224/196984934-e5bfd641-feaf-4dce-993f-083c31932bc3.png">
</p>

  <img src="https://user-images.githubusercontent.com/101813544/197014329-344cd70c-2094-46bb-9e47-6e2e605ef891.png" width="34" height="34"> 3.2). Training Data Pre-processing and Augmentation
  * Pre-processing: Using Keras preprocessing function in each pre-trained CNN model. 
  * Data Augmentation: To increase diversity in the training dataset and let the model learn the data better, the images should be augmented, or transformed, i.e., randomly flipping and rotating them. 
  * Keras' Sequential API was used for data augmentation in this project. Layers are listed below;
    - random horizontal flip
    - random rotation
    - random contrast
    - random zoom
  * Take a look at how an image from the training set has been augmented with simple transformations:

<p align="center">
  <img width="400" height="550" src="https://user-images.githubusercontent.com/88955224/196985415-01b6c275-e030-4fff-970c-c8a53e9add8c.png">
</p>

  <img src="https://user-images.githubusercontent.com/101813544/197014329-344cd70c-2094-46bb-9e47-6e2e605ef891.png" width="34" height="34"> 3.3). Pre-trained Models
  * Objective: To optimize loss function (categorical_crossentropy)
  * Performance metric: Accuracy score
  #### <img src="https://user-images.githubusercontent.com/101813544/197015168-e25a1546-2232-4cbf-aa87-145d90f3d9e8.png" width="18" height="18">  3.3.1) VGG16

       Input properties and train parameters
       Processor = RTX3060 Ti with memory 8GB
       Input image size 256* 256
       Batch size 32
       Optimizer = adam
       Epoch = 20
       loss function = categorical_crossentropy
       Metric = accuracy
   * Base Model Tuning
     - Unfreezed “block5_conv3” layer
   * FC Layers
     - Dense Layer 512 Nodes with Relu activation function
     - Dropout 40%
     - Dense Layer 128 Nodes with Relu activation function
     - Dropout 40%
     - Dense Layer 64 Nodes with Relu activation function
     - Dense Layer 8 Nodes with Softmax activation function
   * VGG16 Results
     - Traintime : 143.7178+-0.9595

<p align="center">
  <img width="650" height="160" src="https://user-images.githubusercontent.com/88955224/196987534-998915fe-e2aa-4f0b-ad72-10354f84a2de.PNG">
</p>
<p align="center">
  <img width="650" height="300" src="https://user-images.githubusercontent.com/88955224/196987685-3da78229-55ed-4e63-8bf1-f5225a0ccf61.png">
</p>

  #### <img src="https://user-images.githubusercontent.com/101813544/197015168-e25a1546-2232-4cbf-aa87-145d90f3d9e8.png" width="18" height="18"> 3.3.2) EfficientNetB0
       Input properties and train parameters
       Processor = GTX 1650 Ti
       Input image size 256* 256
       Batch size 64
       Epoch = 80
       Pooling = Average
   * Base Model Tuning
     - Unfreezed “block7a_se_excite“ layer
   * FC Layers
     - Dropout 40%
     - Dense Layer 8 Nodes with Softmax activation function
   * EfficientNetB0 Results
     - Traintime : 4823.88+-452.939
<p align="center">
  <img width="650" height="160" src="https://user-images.githubusercontent.com/88955224/196988508-019e5275-a1c0-4316-9dd1-5939da834250.PNG">
</p>
<p align="center">
  <img width="650" height="300" src="https://user-images.githubusercontent.com/88955224/196988640-b704c6f1-d330-48de-b29e-9590dddfa13e.png">
</p>

  #### <img src="https://user-images.githubusercontent.com/101813544/197015168-e25a1546-2232-4cbf-aa87-145d90f3d9e8.png" width="18" height="18"> 3.3.3) ResNet50
       Input properties and train parameters
       Processor = RTX3060 Ti  with memory 8GB
       Input image size 224 * 224 
       Batch size 32
       Optimizer = adam
       Epoch = 50
       loss function = categorical_crossentropy
       Metric = accuracy
   * Base Model Tuning
     - Unfreezed “conv5_block3_3_conv“ layer
     - Unfreezed “conv5_block3_3_bn“ layer 
   * FC Layers
     - Dense Layer 512 Nodes with Relu activation function
     - Dense Layer 128 Nodes with Relu activation function
     - Dropout 50%
     - Dense Layer 64 Nodes with Relu activation function
     - Dense Layer 8 Nodes with Softmax activation function
   * ResNet50 Results
     - Traintime : 302.518+-4.1259

<p align="center">
  <img width="650" height="160" src="https://user-images.githubusercontent.com/88955224/196989301-c6f18841-4536-46a6-ae70-65a45d4192f6.PNG">
</p>
<p align="center">
  <img width="650" height="300" src="https://user-images.githubusercontent.com/88955224/196989292-6d56789c-20ec-479b-ae81-0faa9aaebc50.png">
</p>

  #### <img src="https://user-images.githubusercontent.com/101813544/197015168-e25a1546-2232-4cbf-aa87-145d90f3d9e8.png" width="18" height="18"> 3.3.4) MobileNetV2
       Input properties and train parameters
       Processor = Tesla 64C  with memory 16GB
       Input image size 256 * 256 
       Batch size 32
       Optimizer = adam
       Epoch = 20
       loss function = categorical_crossentropy
       Metric = accuracy
   * Base Model Tuning
     - Unfreezed from layer 20 onwards
     - Unfreezed BatchNormalization layers
     - Optimizer: adam=0.0001
   * FC Layers
     - Dense Layer 512 Nodes with Relu activation function
     - Dropout 40%
     - Dense Layer 256 Nodes with Relu activation function
     - Dropout 20%
     - Dense Layer 8 Nodes with Softmax activation function
   * MobileNetV2 Results
     - Traintime : 336.6433+-4.8704
     - 
<p align="center">
  <img width="650" height="160" src="https://user-images.githubusercontent.com/88955224/196990088-c2dfbbed-0d01-4e12-9466-9aa9a93be98c.PNG">
</p>
<p align="center">
  <img width="650" height="300" src="https://user-images.githubusercontent.com/88955224/196990075-b4135541-3876-4133-a9f2-a429f25a8158.png">
</p>

  #### <img src="https://user-images.githubusercontent.com/101813544/197015168-e25a1546-2232-4cbf-aa87-145d90f3d9e8.png" width="18" height="18"> 3.3.5) InceptionResNetV2
       Input properties and train parameters
       Processor = Tesla 64C  with memory 16GB
       Input image size 256 * 256 
       Batch size 32
       Optimizer = adam
       Epoch = 20
       loss function = categorical_crossentropy
       Metric = accuracy
   * Base Model Tuning
     - Unfreezed from layer 100 onwards
     - Optimizer: adam=0.0001
   * FC Layers
     - Dense Layer 512 Nodes with Relu activation function
     - Dense Layer 128 Nodes with Relu activation function
     - Dropout 50%
     - Dense Layer 64 Nodes with Relu activation function
     - Dense Layer 8 Nodes with Softmax activation function
   * InceptionResNetV2 Results
     - Traintime : 401.1403+-3.9203
     - 
<p align="center">
  <img width="650" height="160" src="https://user-images.githubusercontent.com/88955224/196990748-96bc2f47-56f2-4813-988a-71d5ec9a62a7.PNG">
</p>
<p align="center">
  <img width="650" height="300" src="https://user-images.githubusercontent.com/88955224/196990753-1677eeec-66c9-41e4-a9e8-5c323f695f26.png">
</p>

## <img src="https://user-images.githubusercontent.com/101813544/197008423-3f4f5b4a-0481-4e63-8448-2d3b9ac32a22.png" width="40" height="40"> 4). Results
  * Total 5 pre-trained CNN models were performed on the posture buddha images dataset (VGG16, EfficientNetB0, ResNet50, MobileNetV2, and InceptionResNetV2). 
  * Pre-trained accuracy results range from 61% to 73%. Loss values range from 0.75 to 1.20. The best model with lowest loss value and highest accuracy score is EfficientNetB0.
  * After tuning accuracy results range from 67% to 82%. Loss values range from 0.72 to 1.08. The best model with lowest loss value and highest accuracy score is InceptionResNetV2. 

<p align="center">
  <img width="580" height="380" src="https://user-images.githubusercontent.com/88955224/196991021-92b5f345-c388-453d-aeab-5cde6a7c6eb4.png">
</p>

## <img src="https://user-images.githubusercontent.com/101813544/197008423-3f4f5b4a-0481-4e63-8448-2d3b9ac32a22.png" width="40" height="40"> 5). Discussion and Conclusion
  * Based on results, accuracy scores and loss values obtained from after-tuned models improve from pre-trained for all 5 CNN models, where each model used different tuning parameters. 
  * Accuracy score improvements range from 4% to 34%, where the most improvement came from the InceptionResNetV2 model.
  * Observation: 
    - The InceptionResNetV2 model is tuned by unfreezing the most layers compared to other models.  
    - However, when trying to increase unfreezing layers in other models, i.e. ResNet50, the accuracy score decreased.
  * To conclude, tuning parameters improved optimizing loss values and accuracy scores in all models, which could be resulted from differences between custom dataset and trained ImageNet. 
    - The optimal tuning parameters are different in different models and datasets. 
    - However, a common tuning strategy is to start unfreezing from the layer closest to the FC (Fully Connected) layers, and then refit the model and observe accuracy score. Repeat this step if the accuracy score increases. If not, stop or consider tuning other parameters. 


## <img src="https://user-images.githubusercontent.com/101813544/197011989-691c320f-ec9e-4666-ba75-c8ed63f03fc9.png" width="36" height="36"> Team Members

6410422014 (24%): Coding Master, Train Model

6410422012 (22%): Code Reviewer, Train Model

6410422019 (18%): Report Leader, Train Model

6410422023 (18%): Report main contributor, Train Model

6410422035 (18%): Dataset Review, Train Model

This project is a part of subject DADS7202. Data Analytics and Data Science. NIDA

## Reference
[Keras CNN Application API](https://keras.io/api/applications/)

[Imagenet classes](https://deeplearning.cms.waikato.ac.nz/user-guide/class-maps/IMAGENET/)

กรมศิลปากร กระทรวงวัฒนธรรม. พระพุทธรูปปางต่างๆ พิมพ์ครั้งที่ 4. กรุงเทพฯ : รุ่งศิลป์การพิมพ์ (1977), 2558.



