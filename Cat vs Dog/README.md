# Image-classification
## Transfer learning with VGG16 and fine-tuning for cat vs. dog image classification, optionally using data augmentation.

🐶🐱 Dogs vs. Cats Classification with VGG16


This project classifies images of dogs and cats using transfer learning with the VGG16 model in TensorFlow/Keras.

### 1. Data Setup

Downloaded dataset via Kaggle API.

Extracted and loaded using image_dataset_from_directory.

Images resized and normalized to [0, 1].

### 2. Model Architecture

Used VGG16 (pretrained on ImageNet, include_top=False) as a feature extractor.

Frozen base layers initially to retain pretrained features.

Added custom head:

Flatten layer

Dense (ReLU)

Dense (Sigmoid) for binary classification

### 3. Fine-Tuning

Unfroze VGG16 layers from block5_conv1 onwards.

Allowed model to adapt to dataset while leveraging pretrained knowledge.

### 4. Training & Evaluation

Compiled with RMSprop, binary cross-entropy, and accuracy.

Trained on training set with validation on test set.

Plotted accuracy/loss curves.

### 5. Data Augmentation 

Used ImageDataGenerator with:

Rescaling, shearing, zooming, horizontal flips, etc.

Retrained to improve generalization.
