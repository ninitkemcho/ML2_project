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

### Regular CNN
- We implemented a 4-layer Convolutional Neural Network (CNN) tailored for brain MRI image classification. The architecture includes:
- 4 convolutional blocks with increasing filters: 32 → 64 → 128 → 256
- Each block uses:Conv2d + BatchNorm + ReLU + MaxPooling
- Dropout (p=0.5) to prevent overfitting
- Fully connected layers:FC(256×4×4 → 512) → FC(512 → 128) → FC(128 → 4)
- The final layer outputs logits for 4 classes: Glioma, Meningioma, Pituitary, No Tumor

### ResNet
We also fine-tuned a pretrained ResNet18 model:
- Modified input layer to accept grayscale (1-channel) MRI images
- Replaced final layer to output 4 tumor classes
- Benefits:
-- Enables training deeper networks
-- Solves vanishing gradient via skip connections
-- Achieved higher accuracy and generalization vs custom CNN


### Picture Transformation
Data augmentation is used for preventing overfitting and adding regularization. 
1. Random rotation with +-15 degrees
2. Vertical and Horizontal flip with 50% probability'
3. Grayscale conversion, resizing to 224×224
-- Normalization: scaled pixel values to [-1, 1]
   

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
