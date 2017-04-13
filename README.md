## Solution to [*The Nature Conservancy Fisheries Monitoring*](https://www.kaggle.com/c/the-nature-conservancy-fisheries-monitoring) Kaggle Competition


### Model description
1. Pre-trained models including Vgg16, ResNet50 and InceptionV3 are used to extract convolutional features. Based on model selection result, InceptionV3 is not considered in the final ensemble model.
2. Fully-convolutional networks are trained to convert convolutional features from pre-trained model to final prediction. One version of fully-convolutional network is used to deal with Vgg16 convolutional features. Three versions of fully-convolutional network are used to deal with ResNet50 convolutional features, including one with bounding-box as an extra output.
3. For the version for Vgg16 and the first two versions for ResNet50, models are trained 100 times, respectively. For the last version for ResNet50, models are trained 200 times. A total of 500 models are ensembled (taking average of predictions) in the final.


### Platform and package
Platform: AWS EC2 p2.xlarge
Package: keras v1.1.0, theano v0.8.2
