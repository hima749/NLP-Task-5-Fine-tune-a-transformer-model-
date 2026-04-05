# NLP-Task-5-Fine-tune-a-transformer-model-
# Token Classification using DistilBERT (POS Tagging & Chunking)

## Overview
In this project, I implemented a token classification system using a transformer model (DistilBERT). The goal was to perform sequence labeling tasks such as POS tagging and chunking-like entity recognition.

The model was trained on the CoNLL-2003 dataset and is capable of identifying entities such as persons, organizations, and locations.

---

## Objective
The main objectives of this project were:
- To understand token classification using transformer models
- To implement POS tagging / chunking concepts
- To handle tokenization and label alignment challenges
- To evaluate model performance using sequence-based metrics

---

## Dataset
I used the CoNLL-2003 dataset (via tner version from Hugging Face).

It contains:
- Tokens (words)
- Labels such as:
  - B-PER (Person)
  - B-ORG (Organization)
  - B-LOC (Location)
  - O (Non-entity)

---

## Model Used
- DistilBERT (distilbert-base-uncased)
- Hugging Face Transformers

DistilBERT was chosen because it is lightweight and faster, making it suitable for systems with limited resources.

---

## Methodology

### 1. Tokenization
The dataset was tokenized using the DistilBERT tokenizer.

### 2. Label Alignment
Since BERT splits words into subwords, labels were aligned carefully:
- First token → assigned label
- Remaining subwords → assigned -100 (ignored during training)

### 3. Training
The model was fine-tuned using Hugging Face Trainer.

Due to system limitations (8GB RAM), a smaller subset of the dataset was used.

### 4. Evaluation
The model was evaluated using seqeval metrics:
- Precision
- Recall
- F1 Score

---

## Results

Example:

Input:
John works at Google in California

Output:
John → B-PER  
Google → B-ORG  
California → B-LOC  

The model correctly identified named entities in the sentence.

---

## Challenges Faced
- Handling subword tokenization
- Aligning labels correctly
- Memory limitations (8GB RAM)
- Dataset loading issues due to library versions

---

## Key Learnings
- Transformers require careful preprocessing for token classification
- Label alignment is critical for correct training
- DistilBERT provides a good balance between speed and performance

---

## Comparison: POS vs Chunking

POS Tagging:
- Assigns grammatical roles (NOUN, VERB)
- Word-level

Chunking:
- Groups words into phrases (NP, VP)
- Phrase-level and more complex

---

## Conclusion
This project demonstrates how transformer models can effectively perform sequence labeling tasks. Even with limited resources, efficient models like DistilBERT can achieve good performance.

---

## Author
Himanshu Singh
