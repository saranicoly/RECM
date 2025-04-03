# RECM - Music Genre Classificator

## Introduction

This project aims to develop a music genre classification model based on audio analysis. A dataset containing recordings of different musical genres was used to extract relevant features to train a classifier.

## Methodology

### 1. Dataset

The dataset used is [GTZAN](https://www.kaggle.com/datasets/andradaolteanu/gtzan-dataset-music-genre-classification), which contains audio files from 10 musical genres (blues, classical, country, disco, hip-hop, jazz, metal, pop, reggae, and rock).

### 2. Preprocessing

The GTZAN dataset has already been processed, but for the classifier to work with user-input audio, additional preprocessing is required to handle noise, background sounds, and echoes.

**Steps taken:**
- **Signal normalization:** Adjusting the signal amplitude to a standardized range to prevent extreme volume variations from affecting feature extraction.
- **Noise removal:**
  - **Low-pass filter:** Reduces high-frequency noises such as hissing and whistling.
  - **Spectral Gating:** Removes constant background noise.

![Audio Before Preprocessing](https://github.com/user-attachments/assets/4ba41ea8-a48f-4ec7-ab20-e9c8c3c924d1)  
Audio Before Preprocessing

![Audio After Preprocessing](https://github.com/user-attachments/assets/93ed8b97-f65f-4009-98b2-394afba8a775)  
Audio After Preprocessing

### 3. Feature Extraction

RandomForest was used to evaluate the most relevant features for classification. The 20 most important features were selected, and a correlation matrix was applied. Features with a correlation above 75% were removed, resulting in a final set of 12 features.

![Correlation Matrix](https://github.com/user-attachments/assets/51f1a4f1-a8e4-40e3-9b69-913573b7ab7a)  
Correlation Matrix

### 4. Model Training

A **RandomForest classifier** was trained with 80% of the data, while the remaining 20% was used for validation.

## Results

After training and testing, the model achieved **73% accuracy**, demonstrating good performance even with noisy audio inputs.

![Confusion Matrix](https://github.com/user-attachments/assets/0fc928e8-a324-486e-952b-698047e874d0)  
Confusion Matrix

![Classification Report](https://github.com/user-attachments/assets/185ac2a9-66af-4caf-ab71-931c3b36950b)  
Classification Report

## How to Run

To run this project, follow these steps:

1. Open the `recm.ipynb` file in a Jupyter Notebook or Google Colab.
2. Generate an API key on [Kaggle](https://www.kaggle.com/).
3. Download the `kaggle.json` file and upload it to the notebook.
4. Run all the cells in the notebook.

To test the model with an audio file, simply upload your audio file in the notebook (the code specifies where to do this).

That's it! 🚀 Feel free to contribute.
