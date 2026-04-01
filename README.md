# Contextual Word Sense Disambiguation using T5 Transformer
Project for the course 1164 EEE G513 - ML for Electrical Engineering

## Overview
Natural language often contains ambiguous words whose meanings depend on context. This project builds a Transformer-based NLP system using the T5 (Text-to-Text Transfer Transformer) model to automatically determine the correct meaning of a word in a given sentence.

The task is formulated as a text-to-text problem, where the model predicts whether a target word has the same meaning across two sentences.

## Problem Statement
Traditional NLP systems struggle to capture contextual relationships between words, leading to incorrect interpretations.

Goal:
- Understand contextual semantics
- Detect whether a word has the same or different meaning across sentences
- Improve performance on Word Sense Disambiguation (WSD) tasks

## Dataset
Dataset Used: WiC (Word-in-Context), part of the SuperGLUE benchmark

Each sample contains:
- A target word
- Two sentences containing that word
- A label:
  - 1 → Same meaning
  - 0 → Different meaning

Dataset Statistics:
- Training samples: 5,428  
- Validation samples: 638  
- Test samples: 1,400  

## Model Architecture
Model: T5 Transformer (Encoder-Decoder)

Key Features:
- Text-to-text framework
- Self-attention mechanism
- Positional encoding
- Encoder-decoder architecture

The encoder processes input sentence pairs, and the decoder generates classification output ("Yes" or "No").

## Methodology

### Data Preprocessing
- Cleaned and structured WiC dataset
- Converted into text-to-text format
- Tokenized using T5 tokenizer
- Created PyTorch DataLoaders

### Exploratory Data Analysis (EDA)
- Analyzed word distribution
- Studied sentence structures
- Checked label balance

### Model Training
- Fine-tuned pretrained T5 model
- Used PyTorch and Hugging Face Transformers

### Hyperparameter Optimization
- Learning Rate: 9.76e-5
- Batch Size: 16
- Dropout: 0.45
- Optimizer: Adam

## Results

| Model Version  | Train Accuracy | Validation Accuracy | Test Accuracy |
|---------------|---------------|---------------------|--------------|
| Without Layer | 95.81%        | 95.25%              | 64.21%       |
| With Layer    | 81.13%        | 80.02%              | 65.71%       |

Key Observations:
- Model generalization improves with additional layers
- Slight improvement in test accuracy
- Overfitting is reduced

## Error Analysis
- Model struggles with highly ambiguous words
- Difficulty with semantically similar sentences

Possible Improvements:
- Data augmentation (paraphrasing)
- Better contextual embeddings
- Larger transformer models


## Team Members
Jaya Krishna B (2022A8PS1439G)

Dinesh Kumar P (2022AAPS0659G)

Arpit Saxena (2022A8PS1140G)
