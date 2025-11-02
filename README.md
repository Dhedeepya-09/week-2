# 🗑️ Waste Classification with TrashNet (Google Colab)

![TensorFlow](https://img.shields.io/badge/TensorFlow-2.x-FF6F00?logo=tensorflow)
![Python](https://img.shields.io/badge/Python-3.10+-blue.svg)
![Kaggle](https://img.shields.io/badge/Dataset-TrashNet-20BEFF?logo=kaggle)
![License](https://img.shields.io/badge/License-MIT-green.svg)

An end-to-end **Google Colab** notebook that trains a **Convolutional Neural Network (CNN)** to classify waste images using the [TrashNet](https://www.kaggle.com/datasets/feyzazkefe/trashnet) dataset from Kaggle.

---

## 🌍 Project Overview

This project automatically:

1. Installs and configures the **Kaggle CLI**  
2. Downloads the **TrashNet** dataset  
3. Prepares `/content/dataset` with `train/val/test` splits  
4. Trains a simple CNN model from scratch  
5. Evaluates with accuracy, precision, recall, and F1 score  
6. Saves trained models (`waste_cnn_model.h5`, `best_waste_cnn.h5`)  
7. Plots training/validation performance  

---

## 🧾 Dataset

**TrashNet** contains 6 categories of recyclable waste:

| Class | Example |
|-------|----------|
| 🧃 Cardboard | shipping boxes |
| 🍾 Glass | bottles & jars |
| 🧲 Metal | cans, tins |
| 📄 Paper | newspapers, sheets |
| 🧴 Plastic | bottles, containers |
| 🗑️ Trash | non-recyclable waste |

📦 Kaggle source → [feyzazkefe/trashnet](https://www.kaggle.com/datasets/feyzazkefe/trashnet)

---

## ⚙️ Quick Start (in Colab)

### 1️⃣ Open Google Colab  
Go to [https://colab.research.google.com](https://colab.research.google.com) and create a new notebook.

### 2️⃣ Enable GPU  
**Runtime → Change runtime type → Hardware accelerator → GPU**

### 3️⃣ Paste the Script  
Copy the full Colab script from this repository into a single code cell.

### 4️⃣ Upload `kaggle.json`  
You’ll be prompted to upload your **Kaggle API token**  
(`Account → API → Create New Token` → download `kaggle.json`).

### 5️⃣ Run the Cell  
The script handles everything: dataset → split → training → evaluation.

---

## 🧠 Model Architecture

A lightweight CNN built from scratch:

| Layer | Details |
|--------|----------|
| Conv2D | 32 filters, 3×3, ReLU |
| MaxPooling2D | 2×2 |
| Conv2D | 64 filters, 3×3, ReLU |
| MaxPooling2D | 2×2 |
| Conv2D | 128 filters, 3×3, ReLU |
| MaxPooling2D | 2×2 |
| Flatten | — |
| Dropout | 0.5 |
| Dense | 128 units, ReLU |
| Dense | 6 units, softmax |

Trained using **Adam** optimizer and **categorical cross-entropy** loss.

---

## 📊 Evaluation

Automatically computed on the test set:

- ✅ Accuracy  
- 📏 Precision (macro)  
- 🎯 Recall (macro)  
- 🧮 F1 Score (macro)

Example:
