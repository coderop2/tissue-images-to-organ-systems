# Tissue Images-to-Organ
Classification and segmentation of Tissue images

Oservations:-
- The reason for Some of the images being misclassified can be due either one or many of the following reasons combined:-
    - Noise in the data
    - Ambiguity in the learning process like when the model is trying to distinguish between the two skin classes (skin_1 and skin_2) due to the high similarity between the images between both theses classes that the classifier is doing a bad job in identifying distinguishing features.
    - But when i did transfer leanring the model performance was boosted significantly because the pretrained model was previously trained on a huge dataset and has a lot of prior knowledge which is being used as transfer learning
    - Overfitting of the model to the training dataset
    - As i am converting the images fro a resolution of 3000x3000x3 to 512x512x3 which makes the images loose a lot of its information due to dimentionality reduction
    - Inaccurate data
    - Data duplicacy
    - Imbalanced Data (although this is not happening here as all the classes have 100 images)
    
- Some other observations:-
    - When we do transfer learning the model performance might get boosted significantly as we now have some prior information to start on instead of doing some random initilization and starting from there.
    - Doing parallel loading and unloading of data on gpu makes the training process a whole lot faster and easier (here this is done through the tfds module of tensorflow)


Performance boost by studying Confusion Matrix:-
<p align="center">
  <img src="https://github.com/coderop2/tissue-images-to-organ-systems/blob/main/images/custom_model.png" width="350" title="Custom model confusion matrix">
  <img src="https://github.com/coderop2/tissue-images-to-organ-systems/blob/main/images/vgg.png" width="350" alt="VGG model confusion matrix">
</p>
