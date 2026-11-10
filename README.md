# Brain Tumor Classification with Fine-Tuned MobileNetV2

A deep learning project comparing transfer-learning architectures for four-class brain MRI image classification, developed for **COMP 8610 — Neural Networks & Deep Learning** at the University of Windsor (October 2025).

> **Research/educational project only.** This model has not been clinically validated and must not be used for medical diagnosis.

## Project overview

The project uses a publicly available brain tumor MRI dataset containing **7,023 images** across four classes:

- Glioma
- Meningioma
- Pituitary tumor
- No tumor

The primary approach fine-tunes **MobileNetV2** pretrained on ImageNet and compares it with DenseNet121, DenseNet169, EfficientNetB0, and ResNet50/ResNet50V2 architectures.

## Methodology

1. Split the dataset into **4,569 training**, **1,143 validation**, and **1,311 test** images.
2. Resize images to **224 × 224** and normalize pixel values.
3. Apply training-time augmentation, including Gaussian noise, Gaussian blur, and downsampling/upsampling.
4. Use an ImageNet-pretrained MobileNetV2 backbone with a classification head incorporating global average pooling, dropout, and dense layers.
5. Compare training configurations using different optimizers, activation functions, learning rates, and batch sizes.
6. Evaluate model performance using accuracy, precision, recall, F1 score, AUC, and confusion matrices.

## Best reported MobileNetV2 configuration

| Hyperparameter | Value |
| --- | --- |
| Image size | 224 × 224 |
| Epochs | 15 |
| Optimizer | Adam |
| Learning rate | 0.0001 |
| Activation | ReLU |
| Batch size | 32 |

## Reported results

The following figures are reproduced from the course project report; they have **not** been independently rerun or verified for this repository.

| Model | Accuracy | F1 score | Precision | Recall |
| --- | ---: | ---: | ---: | ---: |
| MobileNetV2 | **99%** | **99.50%** | 99.00% | 99.25% |
| DenseNet121 | 98% | 98.50% | 98.00% | 98.50% |
| DenseNet169 | 97% | 96.75% | 97.25% | 96.75% |
| ResNet50 | 98% | 97.75% | 98.00% | 98.00% |
| EfficientNetB0 | 83% | 78.75% | 85.75% | 81.75% |

MobileNetV2 achieved the highest reported accuracy in this comparison. The report also includes confusion matrices and hyperparameter experiments.

## Dataset

Source: **Brain Tumor MRI Dataset (Kaggle)**. Add the exact dataset URL used in the experiment here before publishing.

The original MRI images are not included in this repository. Download them from the dataset provider and comply with its license and usage terms.

## Code and reproducibility

**Status:** The original training notebooks/source code still need to be added to this repository.

Once available:

1. Download the dataset from its original source.
2. Install the dependencies listed in `requirements.txt` in a suitable Python environment.
3. Update the dataset paths in the notebook or configuration.
4. Run preprocessing, training, and evaluation steps in the provided notebooks.

The exact Python and package versions, random seeds, and any environment-specific setup must be checked against the original code before results can be considered reproducible.

## Project report

The full course report may be added under `report/` after removing student ID numbers and confirming permission to publish shared group work.

## Contributors

- Fangying Lu
- Krittika Barua

This was a collaborative course project. Individual contributions can be documented here once confirmed.

## Future work

- Explore Vision Transformers (ViTs).
- Add explainability methods such as Grad-CAM.
- Evaluate generalization using additional independent datasets.
