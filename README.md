Problem Statement

Many people struggle to recall medication names or get them mixed up, which can pose serious health risks. This project addresses the challenge by developing an image classification model for pharmaceutical drugs and vitamins using Convolutional Neural Networks (CNNs).
The model aims to:
1. Empower individuals to confidently recognize their medications
2. Reduce the likelihood of errors
3. Simplify daily medication routines

Dataset Overview

Our project utilizes a synthetic dataset of labeled images on varied backgrounds. The dataset captures:
1. Shapes: capsules, tablets, and pills
2. Colors: different shades to simulate real-world diversity
3. Forms: vitamins and drugs with different packaging & visual appearances
This synthetic dataset ensures diversity and provides sufficient training variation for the deep learning model to generalize well.

Preprocessing Steps

To prepare images for training, the following augmentations and transformations were applied:
1. Image standardization – balances brightness and contrast
2. Flip (left-right) – adds variability, reducing overfitting risks
3. Crop – introduces variation in scale
4. Resize (224 × 224 × 3) – matches CNN default input dimensions
5. Random contrast – combats over-reliance on lighting
6. Random brightness – simulates different lighting conditions

Modeling

We experimented with two pretrained CNN backbones, ResNet50V2 and EfficientNetB0, using both fully frozen (baseline) and partially frozen (modified) approaches. The final architecture combined GlobalAveragePooling, dense layers, dropout, and a softmax output, trained with the Adam optimizer and EarlyStopping for up to 100 epochs. To improve interpretability, attention maps were generated on the last layers, highlighting how the model identified key features in drug and vitamin images.

Results & Conclusion

1. Fully frozen backbones were not robust enough for multiclass classification.
2. Partially frozen backbones allowed the model to adapt to dataset-specific features.
3. ResNet50V2 (Partially Frozen) achieved the most stable results and the highest evaluation metrics among all approaches.

Dataset: https://www.kaggle.com/datasets/vencerlanz09/pharmaceutical-drugs-and-vitamins-synthetic-images

Model: https://drive.google.com/drive/folders/1reWLJn9z7AEC_L8_JMaSbYBxtqKREpvl?usp=sharing
