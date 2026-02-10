# T5 Text-to-SQL Training Framework

A PyTorch-based training framework for fine-tuning T5 models on text-to-SQL translation tasks.

## Overview

This project provides a complete pipeline for training T5 models to translate natural language queries into SQL statements. It supports both fine-tuning from pretrained checkpoints and training from scratch.

## Features

- Flexible training options: fine-tune pretrained T5 or train from scratch
- Multiple optimizers & schedulers: AdamW with cosine, linear, or no scheduling
- Comprehensive evaluation metrics:
  - SQL Exact Match
  - Record Exact Match
  - Record F1
  - Error Rate
- Early stopping with patience-based termination
- Optional Weights & Biases (W&B) experiment tracking
- Automatic checkpointing of best-performing models

## Requirements

- torch  
- transformers  
- numpy  
- tqdm  
- wandb  
- nltk  

## Data Format

The framework expects the following directory structure:

```text
data/
├── train.nl    # Natural language queries (one per line)
├── train.sql   # Corresponding SQL queries (one per line)
├── dev.nl      # Development set natural language
├── dev.sql     # Development set SQL
├── test.nl     # Test set natural language
└── test.sql    # Test set SQL (for evaluation)
