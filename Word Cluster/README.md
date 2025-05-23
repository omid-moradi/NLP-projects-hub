# 📊 Word Cluster Project

This project demonstrates how to preprocess Persian text data from a news dataset, create word embeddings using Keras, and export the learned embeddings for visualization and further analysis.

---

## 📁 Dataset
- The project uses an Excel file named `news.xlsx` containing Persian news articles.
- The text data is located in the `Body` column.

## 🧹 Preprocessing Steps
- **Duplicate removal:** Ensures only unique news articles are used.
- **Stopword filtering:** Custom stopwords from `stopwords.txt` are applied.
- **Punctuation removal** and **text normalization** are performed using regular expressions.

## 🧠 Label Preparation
- Labels (`cat` column) are encoded using `LabelEncoder` and one-hot encoded for training.

## 🔡 Tokenization
- The top 10,000 most frequent words are kept using `Tokenizer` from Keras.
- Sequences are padded to a maximum length of 300 tokens.

## 🏗️ Model Architecture
- A simple model with:
  - `Embedding` layer of dimension 25
  - `Flatten` layer
  - `Dense` output layer with softmax activation

## 📈 Training
- Optimizer: Adam
- Loss function: Categorical Crossentropy
- Trained for 10 epochs on 90% of the dataset

## 💾 Output Files

| File Name         | Description                        |
|-------------------|------------------------------------|
| `data.csv`        | Word embedding vectors             |
| `meta_data.csv`   | Words corresponding to embeddings  |


## 🌐 Visualization
You can visualize the embeddings using the [TensorFlow Embedding Projector](http://projector.tensorflow.org/):

1. Upload `data.csv` as the **vectors file**
2. Upload `meta_data.csv` as the **metadata file**
3. Explore clustering and relationships among Persian words interactively!

![PCA](Word%20Cluster/image/pca.png)
![t-SNE](Word%20Cluster/image/tsne.png)


---

## ✅ Requirements
- Python 3.8+
- TensorFlow
- Pandas
- scikit-learn

---

Made with ❤️ for NLP enthusiasts working with Persian text.
