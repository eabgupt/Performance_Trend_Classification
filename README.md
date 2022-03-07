# Performance_Trend_Classification Using CNN

# Introduction
The motivation of doing this project comes from the challenges faced while working on a task in the workplace. One of the activities i do involves looking at the performance trend of  thousands of Wireless Mobile Sites and make sure there is no  impact in the recent trend. The impact could be improved performance, Degraded performance or the peformance is neutral.
The existing methododlogy includes performing an excel based Pre and Post Delta Analysis. The Delta analysis is based on average difference in some Pre and Post KPIs. This can be challenging when it comes to addressing Intermittent or Fluctuating KPI issue. Due to temporary issue performance might be severly degraded for a day or two but might be back to baseline once the issue is resolved. The Delta analysis will still consider such cases as degraded and will include in the analysis list. These type of cases are noise which are not concerning but takes up time because these were flagged by Delta Analysis. 
To address these types of challenges i propose using Image classification using CNN instead of Delta Analysis. The Raw 30 days tabular data will be converted into a line chart and CNN model will learn and be able to classify a line chart into performance, Degraded and Neutral category.

![image](https://user-images.githubusercontent.com/55108824/156958555-1cef8b9c-98f2-48a7-8007-460193be03e0.png)

# Project Methodology
![image](https://user-images.githubusercontent.com/55108824/156958704-7d4154ca-3f78-4d1d-bf24-fea6b2bef422.png)

# Data Understanding
![image](https://user-images.githubusercontent.com/55108824/156958758-65f72c83-7b21-4458-84db-d27ddf0ca368.png)

# Data Preparation
![image](https://user-images.githubusercontent.com/55108824/156958801-ba55c761-3cf9-4169-aafa-512e36bbea90.png)

![image](https://user-images.githubusercontent.com/55108824/156958834-c9d91e0a-f7ab-4bfe-849b-d8b56e1bf4a7.png)

# Modeling

CNN Components: Convolution --> ReLU -->Dropout---> MaxPooling --> Flattening --> Full Connection --> Compiling

I built my model 5 layers deep. As an example, Layer #1 begins with the convolution layer denounced as Conv2D. Conv2D is typically used for CNNs, and it has mandatory parameters that have to be entered which consists of filters, kernel size, strides and padding. Input shape is the height and width of the image and 3 means it’s a colored image. It also contains MaxPooling and Dropout layer. MaxPooling helps the model learn how to recognize an image in any orientation and distortion, while Dense keeps the model keep the model from overfitting by randomly dropping some of the outputs in the layer. If set to 0.5, it means that Dropout set to 50%, so 5 in 10 will be randomly dropped.

Layer #5 introduces Flatten and Dense. Flatten turns the pooling into a 1-dimensional array. Dense is the fully connected layer, which is where pooling and flattening come together and classification happens.

Each layer uses the ReLU function to introduce non-linearity. Images are naturally non-linear, so without ReLU, the images would not be read correctly.

Compiling is the last step before actually running the model, it defines what optimizer is being used, how loss/error/or deviations will be found in the model, and then metrics defines how the model will be evaluated. Metrics was set to 'accuracy' because I want to see how accurate my model is for the problem defined.

![image](https://user-images.githubusercontent.com/55108824/156958873-dfdbb308-451b-4f81-8982-d04e65de7d48.png)

# Evaluation

# Model-1 Sequential API

![image](https://user-images.githubusercontent.com/55108824/156959971-37170801-1805-49ea-91dd-d0a06557fcbc.png)

![image](https://user-images.githubusercontent.com/55108824/156960012-07b269f8-7fa2-46a0-a404-860a1b4e4066.png)

# Model-2 Functional API

![image](https://user-images.githubusercontent.com/55108824/156960073-3a0667ff-8fa7-4340-bd66-4741e2312b69.png)

![image](https://user-images.githubusercontent.com/55108824/156960146-fa3da740-d669-476c-9821-27c83c12cdf6.png)

# Model-3 Transfer Learning InceptionV3

![image](https://user-images.githubusercontent.com/55108824/156960211-ac0e7871-3794-41e3-b911-ee47ad974f4f.png)

# Model-4 Transfer Learning VGG16

![image](https://user-images.githubusercontent.com/55108824/156960287-d0bce603-1bfc-4031-ba71-7514550342ff.png)

# Project Part 2

![image](https://user-images.githubusercontent.com/55108824/156960446-27cd5bdd-b752-4fad-8539-71db1e75c629.png)


# Conclusion

![image](https://user-images.githubusercontent.com/55108824/156960329-2723567a-9124-45d4-8bf3-b740da868675.png)

