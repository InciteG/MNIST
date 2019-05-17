# MNIST

This notebook shows my trial and error while testing the MNIST dataset. 

I begin with a basic logistic regression to classify images.

The baseline model begins at around 90% accuracy but with some PCA and tuning with 5-fold cross validation, the model was able to improve to around 92% accuracy.

The next model I attempt is the KNN classifier, which was able to improve up to 96% overall accuracy. 
Decision tree attempts showed far inferior results compared to linear regression and KNN.

SVM was improved up to 96% accuracy. Kaggle leaderboards show SVM can be improved up to 98% so more work must be done. 

XGboost after tuning was only 95%. Should be able to get it to 98% with better cross-validation and parameter optimization

CNN model up to 99.5% accuracy on test dataset. I did not build the CNN model. I researched and used several different CNN layer structures and this was the best performing one I found.

CNN model utilized data augmentation, batch normalization, learning rate reduction and dropouts to improve.

Layer structure:
Conv2D -> ReLU (32, 3, 3)
Conv2D -> ReLU (32, 3, 3)
MaxPool2D (2,2)
Dropout (0.2)
Conv2D -> ReLU (64, 3, 3)
Conv2D -> ReLU (64, 3, 3)
MaxPool2D (2, 2)
Dropout (0.25)
Conv2D (128, 3, 3)
Dropout (0.25)
Flatten
Dense (128, 'relu')
BatchNormalization
Dropout (0.25)
Dense (10,'softmax') -> output results with 10 class labels in categorical 

Batch size = 64
Epoch = 20
Data augmentation with rotation, zoom, width and height transforms.
