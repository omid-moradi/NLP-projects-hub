# 🇮🇷 NLP in Persian: Introductory Projects

This repository contains two introductory NLP projects specifically designed to demonstrate natural language processing techniques for the **Persian language** using deep learning frameworks like TensorFlow and Keras.

🎯 **Purpose**:  
To showcase practical applications of NLP in Persian, such as **text generation** and **word embedding** for visualization and understanding Persian texts.

---

## 🧠 Persian Poetry Generation

A deep learning model is trained to generate classical Persian poems in the style of **Nasir Khusraw** and **Attar** using character-level LSTM networks.

### 📁 Dataset
- Two `.txt` files:
  - `khosrow.txt` — poems by ناصر خسرو
  - `attar.txt` — poems by عطار نیشابوری

### ⚙️ Preprocessing
- Text cleaning and normalization
- Character-level tokenization with TensorFlow
- Sequence creation using **sliding window**

### 🏗️ Model
- `Embedding` → `LSTM` → `Dense` (Softmax over characters)

### 🏋️ Training
- Loss: `sparse_categorical_crossentropy`
- Optimizer: `Adam`
- Output: generated poems in classical Persian style

### 💡 Sample Output

> Seed: "ای دل"  
> Generated:  
> "ای دل به جهان اگر بدانی / اندر غم و شادی نهانی / شب را به دعا کنی سحر کن / بر نور حقیقتی نشانی"

---

## 📊 Persian Word Embedding and Clustering

This project builds word embeddings from a Persian news dataset and visualizes word clusters using TensorFlow Embedding Projector.

### 📁 Dataset
- `news.xlsx`: Persian news articles (text in `Body` column)

### ⚙️ Preprocessing
- Duplicate removal  
- Stopword filtering using `stopwords.txt`  
- Text normalization and punctuation removal

### 🏗️ Model
- `Embedding (dim=25)` → `Flatten` → `Dense (Softmax)`
- Trained to classify news categories

### 💾 Outputs
| File             | Description                     |
|------------------|---------------------------------|
| `data.csv`       | Word embedding vectors          |
| `meta_data.csv`  | Words associated with vectors   |

### 🌐 Visualization
Use [TensorFlow Embedding Projector](http://projector.tensorflow.org/) to explore clusters:

1. Upload `data.csv` as **vectors**
2. Upload `meta_data.csv` as **metadata**

---

## ✅ Requirements (for both projects)

- Python 3.8+
- TensorFlow 2.x
- NumPy
- Pandas
- scikit-learn
- Google Colab or Jupyter Notebook

---

## 📌 Summary

These projects are built solely for **educational purposes** and serve as a starting point for exploring:

- Text generation with LSTMs in Persian
- Word embeddings and semantic clustering
- Preprocessing challenges unique to Persian script

---

Made with ❤️ for anyone starting NLP with the Persian language.
