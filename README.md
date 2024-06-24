# -ViT-PCOS-Vision-Transformer-for-Automated-Polycystic-Ovary-Syndrome-Detection

The project "ViT-PCOS" aims to utilize Vision Transformers (ViT) for the automated detection of Polycystic Ovary Syndrome (PCOS) from ultrasound images. It seeks to provide a clinical decision support system (CDSS) to enhance diagnostic accessibility in underserved areas. The research demonstrates ViT's superiority over existing methods in learning discriminative features, achieving an impressive 100% accuracy on a test set of ultrasound images, indicating significant potential for deployment in real-world clinical settings.

## Dataset 
The dataset comprises ultrasound images classified into two categories: infected and non-infected. It contains 781 infected and 1143 non-infected images for training, and 787 infected and 1145 non-infected images for testing, sourced from Kaggle. Each image is annotated to indicate its category, providing a clear ground truth for training and evaluating the model.
<p align="center">
    <img src="https://github.com/Lakshmisri01/-ViT-PCOS-Vision-Transformer-for-Automated-Polycystic-Ovary-Syndrome-Detection/assets/114591852/68bdbf11-e9e6-4305-bd77-970208d19e86" alt="Image 1" width="45%">
    <img src="https://github.com/Lakshmisri01/-ViT-PCOS-Vision-Transformer-for-Automated-Polycystic-Ovary-Syndrome-Detection/assets/114591852/44b87cec-6fcc-4186-9399-2428577a903b" alt="Image 2" width="33%">
</p>

[PCOS Dataset on Kaggle](https://www.kaggle.com/datasets/lakshmisri1/pcos-clean-1?resource=download)

**Note** - The corrupted files present in the dataset were manually verified and removed before being fed into the ViT Model.

## Methodology
The "ViT-PCOS" project employs the Vision Transformer (ViT) architecture to analyze ultrasound images for the detection of Polycystic Ovary Syndrome (PCOS). Each image is divided into 16x16 pixel patches, which are then linearly embedded and processed as sequences, incorporating a special classification token for holistic image assessment. Positional encodings are added to maintain spatial relationships between patches. The core of the model is its multi-headed self-attention mechanism, which allows it to focus on the most informative parts of an image. The transformer encoder layers, followed by layer normalization and a multi-layer perceptron (MLP), output a representation that a final classifier uses to predict PCOS presence.Then the model is trained using a cross-entropy loss function.

The attention matrix \( A \) is computed as follows:

![Equation](https://latex.codecogs.com/svg.latex?\color{White}A%20%3D%20%5Ctext%7Bsoftmax%7D%5Cleft%28%20%5Cfrac%7BQK%5ET%7D%7B%5Csqrt%7BD_k%7D%7D%20%5Cright%29%2C%20%5Cquad%20A%20%5Cin%20%5Cmathbb%7BR%7D%5E%7Bn%20%5Ctimes%20n%7D)

![image](https://github.com/Lakshmisri01/-ViT-PCOS-Vision-Transformer-for-Automated-Polycystic-Ovary-Syndrome-Detection/assets/114591852/7d383d53-9e87-4a85-855a-2b66fbc76d62)

## Results 
The Vision Transformer (ViT) model excelled, achieving a 100% accuracy rate by correctly classifying all ultrasound images into two distinct categories: those indicative of Polycystic Ovary Syndrome (PCOS) and those from healthy individuals. The performance was mirrored across other critical metrics such as precision, recall, and the F1-score, each also reaching 100%. These metrics collectively illustrate the model's exceptional capability to identify and differentiate between the presence and absence of PCOS with complete accuracy.

To visually validate and explain the model’s performance, two types of visualization tools were employed: confusion matrices and t-SNE plots. The confusion matrix provided a clear and intuitive presentation of the model’s classification results, showing perfect alignment between the predicted categories and the actual labels, with zero misclassifications. Meanwhile, the t-SNE plot, a technique for dimensionality reduction, was utilized to depict how the model perceives and separates PCOS from non-PCOS images in a two-dimensional space. This plot demonstrated distinct clustering of the two categories, underscoring the model's robust ability to distinguish between complex patterns inherent in the ultrasound images. These visual tools not only reinforced the numerical results but also offered insightful visual evidence of the model’s discriminative power, proving its potential utility in clinical settings for accurate PCOS diagnosis.

### Confusion matrix
<img src="https://github.com/Lakshmisri01/-ViT-PCOS-Vision-Transformer-for-Automated-Polycystic-Ovary-Syndrome-Detection/assets/114591852/02745d3d-9fce-491e-97a1-ccc7679e225e" alt="Confusion Matrix" width="500">

### t-SNE plot
<img src="https://github.com/Lakshmisri01/-ViT-PCOS-Vision-Transformer-for-Automated-Polycystic-Ovary-Syndrome-Detection/assets/114591852/62b20b58-79de-4e2c-95eb-8ee4def0b047" alt="t-SNE Plot" width="500">

### Metrics

Metrics derived from the confusion matrix, including accuracy, precision, recall, and F1-score, were calculated for analysis of the model's classification capabilities.

| **Metric**         | **Value** |
|--------------------|-----------|
| model_name         | ViT-L-16  |
| finetune_all       | True      |
| accuracy           | 1.0       |
| average_f1         | 1.0       |
| average_precision  | 1.0       |
| average_recall     | 1.0       |
| best val acc       | 100.0     |
| loss               | 0.0       |
| val acc            | 100.0     |

**Table 1:** Metrics evaluated on the test set



