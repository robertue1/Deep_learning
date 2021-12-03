# Street sign classification using CNNs


# Abstract

Humans have been driving for more than 150 years, and even when cars have gotten safer, deaths by motor accidents have decreased in general, the number still
surpasses 30.000 a year. As human error is one of the key influencing factors in the accidents, a future of self-driving cars could entirely change the way we 
move, making traveling and commuting a safer and more enjoyable experience. A fundamental factor of autonomous vehicles, is the capability to interpret the 
enviroment and regulations, this is why, a street sign classification system was developed, training different CNNs, choosing the best performing one
and then using some fine tuning of their hyperparameters in order to improve performance. 

# Design

Initially, like in all DS problems, EDA was done in order to get a better sense of the data and possible limiations. A Non-Deep Learning model was developed, after
that, multiple implementations of Convolutional Neural Networks were built and tested (including transfer learning), looking for the best performance on the
accuracy score on the test set. The final model was a fine tuned version of the original baseline CNN. 

# Data

* Source:  [German Traffic Sign Recognition Benchmark GTSRB](https://sid.erda.dk/public/archives/daaeac0d7ce1152aea9b61d9f1e19370/published-archive.html)

* Num. Images:  53000 (Total, for training, validation and test). 

* Num Labels:  43


# Methodology and Algorithms

The first approach, was to use a RF model, obtaining an accuracy of 0.776 on the test set after using RandomSearch for hyperparamenter tuning. After that, 
a base Convolutional Neural Network was built, obtaining a 0.881 score on the test set. After using Transfer Learnin with two variations of models (ResNet-50 and VGG16), 
and obtaining accuracy scores below 0.60, the base CNN was fine tuned, adding dropout layers and a dynamic Learning Rate, the model scores 0.94 for accuracy 
on the test set. 

# Tools
Analysis:  Tensorflow Keras, Scikit Learn, Numpy
Visualization:  Matplotlib, Seaborn

# Results

Classification report from the final model are provided below:

precision    recall  f1-score   support

                              Speed limit (20km/h)       0.98      0.83      0.90        60
                              Speed limit (30km/h)       0.93      0.98      0.95       720
                              Speed limit (50km/h)       0.93      0.96      0.94       750
                              Speed limit (60km/h)       0.87      0.96      0.92       450
                              Speed limit (70km/h)       1.00      0.94      0.97       660
                              Speed limit (80km/h)       0.91      0.89      0.90       630
                       End of speed limit (80km/h)       0.99      0.83      0.91       150
                             Speed limit (100km/h)       0.94      0.87      0.90       450
                             Speed limit (120km/h)       0.88      0.96      0.92       450
                                        No passing       0.95      0.96      0.96       480
      No passing for vehicles over 3.5 metric tons       0.98      0.98      0.98       660
             Right-of-way at the next intersection       0.92      0.98      0.95       420
                                     Priority road       0.99      0.96      0.98       690
                                             Yield       0.98      0.99      0.99       720
                                              Stop       1.00      1.00      1.00       270
                                       No vehicles       0.89      0.99      0.94       210
          Vehicles over 3.5 metric tons prohibited       0.94      0.99      0.96       150
                                          No entry       0.99      0.99      0.99       360
                                   General caution       0.96      0.92      0.94       390
                       Dangerous curve to the left       0.93      0.93      0.93        60
                      Dangerous curve to the right       0.83      0.94      0.89        90
                                      Double curve       0.93      0.59      0.72        90
                                        Bumpy road       0.93      0.92      0.92       120
                                     Slippery road       0.87      0.81      0.84       150
                         Road narrows on the right       0.96      0.54      0.70        90
                                         Road work       0.94      0.94      0.94       480
                                   Traffic signals       0.74      0.84      0.78       180
                                       Pedestrians       0.84      0.60      0.70        60
                                 Children crossing       0.97      0.95      0.96       150
                                 Bicycles crossing       0.79      0.94      0.86        90
                                Beware of ice/snow       0.78      0.67      0.72       150
                             Wild animals crossing       0.88      0.93      0.91       270
               End of all speed and passing limits       0.95      1.00      0.98        60
                                  Turn right ahead       0.96      1.00      0.98       210
                                   Turn left ahead       0.85      0.99      0.92       120
                                        Ahead only       0.98      0.97      0.98       390
                              Go straight or right       0.98      0.98      0.98       120
                               Go straight or left       0.98      0.97      0.97        60
                                        Keep right       0.99      0.97      0.98       690
                                         Keep left       0.91      0.89      0.90        90
                              Roundabout mandatory       0.95      0.87      0.91        90
                                 End of no passing       0.86      0.73      0.79        60
                End of no passing by vehicles over       0.93      0.92      0.93        90

                                          accuracy         _        _        0.94     12630
                                         macro avg       0.93      0.90      0.91     12630
                                      weighted avg       0.94      0.94      0.94     12630
