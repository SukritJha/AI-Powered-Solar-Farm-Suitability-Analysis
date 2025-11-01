# 🛰️ AI-Powered Solar Farm Suitability Analysis

This is an advanced deep learning project built for my Shell internship. It uses a Convolutional Neural Network (CNN) to analyze satellite images and automatically classify land based on its suitability for renewable energy (solar farm) development.

This project is an advanced version of a simple land-use classifier. It is specifically "re-tooled" to solve a business-relevant problem for Shell's **Energy Transition** strategy: **automating and accelerating the site-scouting process for new solar projects.**

## 🎯 The Business Problem

Finding new locations for solar farms is a slow, manual, and expensive process. It requires analysts to scan thousands of square kilometers of satellite imagery to find open, flat, non-forested, and non-residential land. This "site scouting" is a major bottleneck in renewable energy expansion.

## 💡 Our AI Solution

This project solves the problem with a "Geo-AI" model. I took a powerful pre-trained CNN (`MobileNetV2`) and re-trained it on the EuroSAT satellite dataset.

Instead of classifying 10 generic land types, I re-mapped all 27,000 images into **three new, business-relevant categories:**

1.  **`Good_for_Solar`** (Open land, pastures, etc.)
2.  **`Bad_for_Solar`** (Forests, residential, and industrial areas)
3.  **`Unusable_Land`** (Water, highways, etc.)

The result is a fast, automated tool that can "scout" any new satellite image in seconds and provide a first-pass analysis of its suitability for a solar farm.

---

## 📊 Key Results

The model was highly successful and achieved a **final test accuracy of [Your Accuracy]%**. *(e.g., 95.4%)*

### 1. Classification Report & Confusion Matrix

The model is extremely effective at identifying `Good_for_Solar` land. The confusion matrix shows that the vast majority of its (few) errors are logical, such as confusing `Unusable_Land` (like a `PermanentCrop`) with `Bad_for_Solar` (like a `Forest`).

<img width="658" height="547" alt="image" src="https://github.com/user-attachments/assets/2c9ad791-0cbf-4a8c-86c4-76663cdbc0b5" />

``

### 2. Model Performance Graphs

The accuracy and loss graphs show a perfect, healthy training curve. The validation and training lines track closely together, proving the model **learned the concepts** and is **not "memorizing"** (overfitting).

<img width="1010" height="470" alt="image" src="https://github.com/user-attachments/assets/b989191f-47b2-45d1-8468-25b274470ead" />

``

### 3. Prediction Examples

The model correctly analyzes new images, matching its prediction (e.g., `Good_for_Solar`) to the true land type (e.g., `Pasture`).

<img width="1136" height="1190" alt="image" src="https://github.com/user-attachments/assets/608c56d9-b4f5-4b0e-a27b-f974ce6742b2" />

``

---

## 🛠️ Technology Stack

* **Language:** Python
* **AI Frameworks:** TensorFlow & Keras
* **Core Model:** Convolutional Neural Network (CNN) - `MobileNetV2` (via Transfer Learning)
* **Libraries:** `TensorFlow Datasets` (Data), `Matplotlib` (Plotting), `Seaborn` (Reports), `NumPy`
* **Environment:** Google Colab (with T4 GPU)
* **Dataset:** EuroSAT (27,000 images, 10 original classes re-mapped to 3 new classes)

---

## 🚀 How to Run

The entire project is contained in the `.ipynb` notebook file.

1.  Upload the `.ipynb` file to [Google Colab](https://colab.research.google.com/).
2.  Ensure the runtime is set to **T4 GPU** (`Runtime > Change runtime type`).
3.  Run all cells from top to bottom (`Runtime > Run all`).
4.  You can test the model on your own images using the **"Upload Image"** button at the end of the notebook.
