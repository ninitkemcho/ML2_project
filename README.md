# Brain Tumor Detection

## Project Structure
```
Brain Tumor Detection
├── Brain Tumor Detection.ipynb
├── Brain Tumor Detection.pptx
└── README.md
```

### Data Loading
Every step, including data loading part, is in ` Brain Tumor Detection.ipynb `. For reproducibility data is downloaded from kaggle, saved to google colab runtime. You will need kaggle account to upload ` kaggle.json ` to google colab code. All relative pathes are set accordingly.

## Model Structure
Regular CNN is trained with several layers of convolutional layer (32 to 256 filters), pooling layer and batch normalization

### Picture Transformation
Data augmentation is used for preventing overfitting and adding regularization. 
1. Random rotation with +-15 degrees
2. Vertical and Horizontal flip with 50% probability
   
### ResNet
Model performance is improved with residual network, which enables:
1. Training deeper neural networks
2. Solving vanishing gradient problem

### Results

```
==================================================
Test Accuracy: 99.02%
Train Accuracy: 98.63%

Per-class accuracies: 
glioma: 97.74% 
meningioma: 98.10% 
pituitary_tumor: 100.00%
no_tumor: 100.00%
==================================================
```
