# Concrete Crack Detection CNN

## Project Overview

This project is developed for the Machine Learning course. The goal is to build a CNN based image classification system that detects whether a concrete surface image contains a visible crack or not.

The project uses a public image dataset and compares a custom CNN model with a transfer learning model based on MobileNetV2. The implementation includes dataset loading, preprocessing, data augmentation, model training, evaluation, confusion matrices, classification reports, model comparison, and Grad CAM explainability.

## Project Topic

Concrete Crack Detection Using CNNs

## Field

Construction and Civil Infrastructure Monitoring

## Dataset

Dataset name: Concrete Crack Images for Classification

Dataset link: https://www.kaggle.com/datasets/arnavr10880/concrete-crack-images-for-classification

The dataset contains concrete surface images divided into two classes.

| Class    | Meaning                | Number of Images |
| -------- | ---------------------- | ---------------: |
| Negative | No visible crack       |            20000 |
| Positive | Visible concrete crack |            20000 |

Total number of images: 40000

Image type: RGB concrete surface images

Task type: Binary image classification

## Repository Structure

```text
concrete-crack-detection-cnn/
│
├── notebooks/
│   └── concrete-crack-detection-cnn.ipynb
│
├── outputs/
│   ├── figures/
│   │   ├── custom_cnn_accuracy_curve.png
│   │   ├── custom_cnn_confusion_matrix.png
│   │   ├── custom_cnn_gradcam_examples.png
│   │   ├── custom_cnn_loss_curve.png
│   │   ├── mobilenetv2_accuracy_curve.png
│   │   ├── mobilenetv2_confusion_matrix.png
│   │   ├── mobilenetv2_loss_curve.png
│   │   └── model_comparison_accuracy.png
│   │
│   └── tables/
│       ├── custom_cnn_classification_report.csv
│       ├── mobilenetv2_classification_report.csv
│       └── model_comparison_table.csv
│
└── README.md
```

## Methodology

The project follows a supervised deep learning workflow.

1. Load the public concrete crack image dataset
2. Create a dataframe with image paths and labels
3. Encode labels as numerical values
4. Split the dataset into training, validation, and test sets
5. Resize images to 160 by 160 pixels
6. Normalize pixel values between 0 and 1
7. Apply data augmentation
8. Train a custom CNN model
9. Train a MobileNetV2 transfer learning model
10. Evaluate both models on the test set
11. Generate confusion matrices and classification reports
12. Compare model performance
13. Apply Grad CAM explainability to the custom CNN model

## Models Used

### Custom CNN

The custom CNN model was developed as the baseline model. It includes convolutional layers, max pooling layers, global average pooling, dropout regularization, and a sigmoid output layer for binary classification.

### MobileNetV2 Transfer Learning

MobileNetV2 was used as the transfer learning model. The pretrained base model was loaded with ImageNet weights and frozen. Only the final classification layer was trained for the concrete crack detection task.

## Results

| Model                         | Test Accuracy | Test Loss | Macro F1 Score | Total Errors |
| ----------------------------- | ------------: | --------: | -------------: | -----------: |
| Custom CNN                    |      0.997667 |  0.008042 |       0.997667 |           14 |
| MobileNetV2 Transfer Learning |      0.998667 |  0.003335 |       0.998667 |            8 |

The MobileNetV2 transfer learning model achieved the best performance with a test accuracy of approximately 99.87 percent.

## Key Output Figures

The repository includes the following output figures.

```text
custom_cnn_accuracy_curve.png
custom_cnn_confusion_matrix.png
custom_cnn_gradcam_examples.png
custom_cnn_loss_curve.png
mobilenetv2_accuracy_curve.png
mobilenetv2_confusion_matrix.png
mobilenetv2_loss_curve.png
model_comparison_accuracy.png
```

## Grad CAM Explainability

Grad CAM was used to visualize which image regions influenced the custom CNN model's predictions. The visualization helps evaluate whether the model focuses on crack like structures or irrelevant texture regions.

The Grad CAM examples include:

1. Correct Positive prediction
2. Correct Negative prediction
3. False Positive prediction
4. False Negative prediction

This supports both explainability and error analysis.

## How to Run

The notebook can be run on Kaggle or another Python environment with TensorFlow support.

Recommended environment:

```text
Python
TensorFlow
Keras
NumPy
Pandas
Matplotlib
scikit learn
```

Steps:

1. Open the notebook in the `notebooks` folder
2. Add the Kaggle dataset as input
3. Run all cells from top to bottom
4. Generated figures and tables will be saved inside the `outputs` folder

## Kaggle Notebook

Kaggle notebook link: https://www.kaggle.com/code/ardaongun/concrete-crack-detection-cnn

## Author

Arda Ongun

Machine Learning Course Phase 2 Project
