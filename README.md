# Banana Ripeness Classification using Transfer Learning

A reproducible implementation of the paper:

> **Ripen banana dataset: A comprehensive resource for carbide detection and ripening stage analysis to enhance food quality and agricultural efficiency** (2025)

This project reproduces the banana ripeness classification experiments using **ResNet-50** and **DenseNet-201** with TensorFlow/Keras in **Google Colab**.

---

## Features

- Reproduction of the published transfer learning pipeline
- ResNet-50 implementation
- DenseNet-201 implementation
- Data augmentation
- Transfer learning using ImageNet pretrained weights
- Fine-tuning experiments
- Performance evaluation using:
  - Accuracy
  - Precision
  - Recall
  - F1-score
  - Confusion Matrix
  - ROC Curve
  - Training & Validation Curves

---

## Paper

**Title**

> Ripen banana dataset: A comprehensive resource for carbide detection and ripening stage analysis to enhance food quality and agricultural efficiency

**Year:** 2025

---

## Tech Stack

- Python
- TensorFlow / Keras
- Google Colab
- NumPy
- Matplotlib
- Seaborn
- Scikit-learn

---

# Dataset

The dataset used in this project is the **Real Dataset** provided by the authors.

Directory structure:

```
Real Dataset/
    train/
        Class A
        Class B
        Class C
        Class D

    validation/
        Class A
        Class B
        Class C
        Class D

    test/
        Class A
        Class B
        Class C
        Class D
```

Dataset is automatically downloaded from the public GitHub repository inside the notebook.

---

# Model Architecture

Both models use transfer learning with ImageNet pretrained weights.

### Backbone

- ResNet-50
- DenseNet-201

### Classification Head

- Global Average Pooling
- Dense (512, ReLU)
- Batch Normalization
- Dropout (0.2)
- Dense (256, ReLU)
- Batch Normalization
- Dropout (0.2)
- Dense (Softmax)

---

# Hyperparameters

| Parameter | Value |
|-----------|------:|
| Image Size | 224 × 224 |
| Batch Size | 32 |
| Optimizer | Adam |
| Learning Rate | 1e-4 |
| Epochs | 50 |
| Dropout | 0.2 |

---

# Results

| Model | Test Accuracy |
|--------|--------------:|
| ResNet-50 | ~74% |
| DenseNet-201 | ~91% |

> DenseNet-201 outperformed ResNet-50 on this dataset.

---

# Repository Structure

```
.
├── BananaRipeness.ipynb
├── README.md
├── requirements.txt
├── saved_models/
│   ├── resnet50_paper.keras
│   ├── densenet201_paper.keras
│   ├── resnet50_finetuned.keras
│   └── densenet201_finetuned.keras
└── results/
```

---

# Running the Project

## 1. Clone the repository

```bash
git clone https://github.com/<your-username>/<repository-name>.git
```

---

## 2. Open Google Colab

Upload or open the notebook:

```
BananaRipeness.ipynb
```

---

## 3. Enable GPU

```
Runtime
    → Change runtime type
        → Hardware accelerator
            → T4 GPU
```

---

## 4. Run all cells

The notebook automatically:

- downloads the dataset
- prepares train/validation/test generators
- builds the models
- trains ResNet-50
- trains DenseNet-201
- evaluates both models
- generates performance metrics and plots
- saves trained models

---

# Installing Dependencies

```bash
pip install -r requirements.txt
```

---

# Saved Models

The repository includes trained models in Keras format.

```
saved_models/
```

These can be loaded using:

```python
from tensorflow.keras.models import load_model

model = load_model("saved_models/densenet201_paper.keras")
```

---

# Future Work

- Improve model robustness under varying illumination
- Fine-tune pretrained backbones
- Explore EfficientNet and Vision Transformers
- Grad-CAM based explainability
- Real-world deployment
- Mobile inference
- Extend the work toward calcium carbide detection

---

# Disclaimer

This repository is a reproduction of the methodology presented in the referenced paper for educational and research purposes.

Any future improvements or extensions will be documented separately.

---

# Author

**Keerthana Salla**

B.Tech Computer Science and Engineering

National Institute of Technology Delhi

---

# License

This project is released under the MIT License.
