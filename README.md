# Tissue Images-to-Organ Mapping
Made by:- Harshit Khandelwal (hkhandel@iu.edu)

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

I have also with the help of TSNE & PCA algorithm plotted each training and testing image on a 2D map. I have taken this a step further by using TSNE & PCA on layer outputs of the model to understand how the model is working on a layer by layer basis.
Like i have 5 layer so i am passing output from each layer (while taking input as the image itself) to TSNE to generate 2 best components and plotting then on the map to see which layer performs the best at identifying the images and explains what pecularity about the dataset.
Since the training data is pretty tightly weaved the custom model is finding it hard to distinguish between each class and easily ends up overfitting.
