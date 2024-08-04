# CNN_KNN_XAI

- This contains the colab file that uses InceptionV3 model for feature extraction and KNN as the classifier.
- Then, we are using XAI (explainable AI) methods, currently LIME and GradCAM (Gradient Class Activation Mapping), to show what our model is learning and the type of features that have been extracted from images for the same.

# CNN Fine Tuning and training of KNN by feature extraction
- After fine tuning the CNN layers, the KNN classifier is to be trained.
- In order to train the same, we first extract the features from the images and then pass those features to KNN classifier. This is done because we have used ***keras*** and not ***Scikit learn***, although it provides easier training of various ML models because:
  1. Scikit-learn does not support GPUs. By building our k-NN in Keras, we can leverage GPUs for increased inference speed.
  2. Running on iOS devices. Although, Apple’s tools for converting Machine Learning models to Apple’s CoreML format do support Scikit-learn but only some specific model types and the k-NN is not one of them.
  3. Building the k-NN in Scikit-learn (or similar) would introduce another dependency. By building the k-NN with the same tools we use for the neural network, we can avoid introducing more dependencies.
  4. Having a single, unified model handling feature extraction and neighbor computation makes for a simpler setup.

