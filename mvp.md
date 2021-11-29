# Baseline for a traffic signs classification model. 


## First approach 

As the first step to try to solve the multiclass classification problem, a *RandomForest* model was built. Images required to be reshaped in order to be 
feasible inputs for the RF. 

After a tranining test split and some parameters tuning of the model, the accuracy results are:
Accuracy on training: 0.9361430803073294
Accuracy on test: 0.8844682478959449

We can see that the model is overfitting, but it is still making good predictions on the test dataset. Below, we will see some classifications made by the model:

<img width="452" alt="Screen Shot 2021-11-29 at 4 54 14 PM" src="https://user-images.githubusercontent.com/34829066/143948923-be0bae09-fe4a-4340-a2ff-a0af5a9f8d11.png">

This one is correct!

<img width="460" alt="Screen Shot 2021-11-29 at 4 54 23 PM" src="https://user-images.githubusercontent.com/34829066/143948946-423ef577-3424-4eeb-a325-cae5395b281d.png">

This one, I'm not sure. 








## Second approach 

Creating a CNN that we will have to be improve until reaching the final model. 

Below, we can see the model summary. 

_________________________________________________________________
 Layer (type)                Output Shape              Param #   
=================================================================
 conv2d_12 (Conv2D)          (None, 30, 30, 32)        896       
                                                                 
 dropout (Dropout)           (None, 30, 30, 32)        0         
                                                                 
 conv2d_13 (Conv2D)          (None, 28, 28, 32)        9248      
                                                                 
 dropout_1 (Dropout)         (None, 28, 28, 32)        0         
                                                                 
 max_pooling2d_10 (MaxPoolin  (None, 14, 14, 32)       0         
 g2D)                                                            
                                                                 
 flatten_10 (Flatten)        (None, 6272)              0         
                                                                 
 dense_20 (Dense)            (None, 100)               627300    
                                                                 
 dense_21 (Dense)            (None, 43)                4343      


Total params: 641,787

Trainable params: 641,787

Non-trainable params: 0
_________________________________________________________________


Below, we can see the  training versus validation accuracy.

<img width="445" alt="Screen Shot 2021-11-29 at 5 01 45 PM" src="https://user-images.githubusercontent.com/34829066/143949930-f894f0df-bbbf-48ed-aea8-b6ea3537dd90.png">


*The original baseline model was overfitting more than the present one I'm showing with the dropout layers, but... we can still see signs of overfitting.*


For this model, the accuracy scores are:

Training set: 0.9989543217118518
Test set: 0.9475059382422802




To try to improve the accuracy of the model, some pre-processing techniques will be used on the original dataset of images, and if there is still room
for improvement, transfer learning will be implemented in order to end with a more robust model. 

