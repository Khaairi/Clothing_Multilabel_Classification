## Clothing Multi-Label Classification
This repository presents the implementation of a multi-label classification model designed to classify clothing attributes. The project was developed as part of the Hology Data Mining 2024 Preliminary Competition, organized by Universitas Brawijaya. It focuses on categorizing images of T-shirts and hoodies from various online stores in Indonesia based on their type (e.g., T-shirt or hoodie) and color (e.g., black, blue, white, etc.).

Model Link: [Hugging Face Model](https://huggingface.co/bwbayu/vit-patch16-244-multilabel_classification)

### Project Overview
Matos Fashion is an emerging startup in the e-commerce fashion sector, currently facing difficulties in managing and categorizing its expanding inventory. The primary focus is on two types of products: T-shirts and hoodies. To streamline operations and improve the customer shopping experience, Matos Fashion aims to develop an automated product classification system based on product images.

To solve these challenges, we created a machine learning-based multi-label classification model using a fine-tuned Vision Transformer (ViT).

---

### Dataset
The dataset consists of **1111 images** divided into training and test sets:

#### **Training Set:**
- **train**: 777 images of T-shirts and hoodies in 5 different colors.
- **train.csv**: A CSV file containing labels for each training image.
  - **id**: Unique ID for each training image.
  - **jenis**: Clothing type (0: T-shirt, 1: Hoodie).
  - **warna**: Clothing color (0: Red, 1: Yellow, 2: Blue, 3: Black, 4: White).

#### **Test Set:**
- **test**: 334 images for classification.

---

### Objective
The primary objectives of this project are:
1. **Image Preprocessing**: Clean the dataset by removing duplicate images.
2. **Multi-Label Classification**: Build a computer vision model to predict both clothing type and color.

---

### Preprocessing Methodology
1. Convert images to RGB format.
2. Identify and remove duplicate images based on pixel values.
3. Perform data exploration:
   - Analyze clothing type distribution.

   ![Clothing Type Distribution](https://github.com/user-attachments/assets/ddcd3b8e-7c14-41b1-ac86-f5d7ec4e916f)

   - Analyze clothing color distribution.

   ![Clothing Color Distribution](https://github.com/user-attachments/assets/c8263e40-dbfb-42e5-92d8-ea62e8f81f71)

4. Apply data transformations:
   - Resize images to 224x224 pixels.
   - Normalize images
5. Configure the classification head of the Vision Transformer (ViT) to predict two labels: one for clothing type and another for clothing color.
6. Define training parameters:
   - Use three different loss functions: binary cross-entropy for clothing type (2 labels: T-shirt and hoodie), cross-entropy loss for clothing color (5 labels), and a custom loss function for exact match prediction.
   - Employ the Adam optimizer with a learning rate of 1e-4 and train for 10 epochs.

---

### Results
1. Achieved an Exact Match Ratio (EMR) of **0.982905**, demonstrating high accuracy in predicting both clothing type and color simultaneously.
2. Ranked in the top 8 out of 196 teams, highlighting the effectiveness of the model.

---
