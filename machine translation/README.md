# 🤖 English-Persian Machine Translation with mBART

This project builds a sequence-to-sequence model using the Hugging Face `transformers` library to translate text from **English to Persian (Farsi)**. The model fine-tunes a pre-trained **mBART** checkpoint on a parallel corpus, learning to generate high-quality translations.

---

## 🧹 Preprocessing

- **Data Cleaning**: Basic text cleaning, such as removing extra whitespace or specific characters.
- **Data Filtering**: Sentences are filtered based on length to create a more uniform dataset for stable training.
- **Tokenization**: Handled by the pre-trained `MBart50Tokenizer`, which converts text into a format suitable for the model.
- **Dataset Creation**: The preprocessed data is converted into a `Dataset` object compatible with the Hugging Face `Trainer` API.

---

## 🏗️ Model Architecture

The core of the project is the `mBART` (Multilingual BART) model, implemented via `AutoModelForSeq2SeqLM`:

- **Encoder-Decoder Transformer**: `mBART` is a powerful transformer-based architecture designed for sequence-to-sequence tasks.

---

## 🏋️ Training

- **Framework**: Fine-tuning is managed by the high-level `Trainer` API from the `transformers` library.
- **Optimizer**: `AdamW` (the default optimizer for the `Trainer`).
- **Training Arguments**: The `TrainingArguments` class is used to configure hyperparameters like learning rate, batch size, and number of epochs.
- **Checkpointing**: The `Trainer` automatically saves model checkpoints during training, allowing for recovery and resumption of the training process.

---

## ✨ Translation (Inference)

- **Model Loading**: The final fine-tuned model and tokenizer are loaded from the saved directory for inference.
- **Translation Function**: A dedicated `translate()` function performs the following steps:
    - Tokenizes the input English text.
    - Feeds the token IDs to the `model.generate()` method.
    - Uses **Beam Search** (`num_beams=5`) to improve the quality of the generated translation.
    - Decodes the output token IDs back into a readable Persian sentence.

---

## 💾 Output Files

| File                          | Description                                                                 |
|-------------------------------|-----------------------------------------------------------------------------|
| `machin_translation.ipynb`    | Main notebook for data processing, training, and evaluation.                |
| `/model/final_mbart_model/`   | Directory containing the final fine-tuned model and tokenizer files.        |

---

## ✅ Requirements

- Python 3.8+
- PyTorch or TensorFlow 2.x
- `transformers`
- `datasets`
- `evaluate`
- `pandas`
- `scikit-learn`
- Google Colab or Jupyter Notebook (GPU Recommended)

---

## 📌 Example Result

> **English:** The international community has called for a ceasefire.  
> **Persian:** سازمان ملل خواستار آتش بس شدند

> **English:** This is a great achievement for our team.  
> **Persian:** اين يک موفقيت بزرگ براي تيم ماست

---

Made with ❤️ to bridge language barriers through modern AI.