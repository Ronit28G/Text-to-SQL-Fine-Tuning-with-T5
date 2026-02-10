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

```
## Usage

### Basic Training

Fine-tune a pretrained T5 model using default settings.

Command:
python train.py --finetune --max_n_epochs 10 --batch_size 16

### Training from Scratch

Train a T5 model from scratch without loading pretrained weights.

Command:
python train.py --max_n_epochs 20 --learning_rate 1e-4 --batch_size 16

### Training with Experiment Tracking

Enable Weights & Biases logging and specify an experiment name.

Command:
python train.py --finetune --use_wandb --experiment_name my_experiment  
--max_n_epochs 10 --patience_epochs 3

### Early Stopping

Training will automatically stop if validation performance does not improve
for a specified number of epochs.

Configuration:
- Set `--patience_epochs` to control early stopping behavior

### Evaluation Only

Run evaluation using the best saved checkpoint on the validation or test set.

Command:
python train.py --evaluate_only --experiment_name my_experiment

### Output Inspection

After training completes, inspect the generated outputs:

- Model checkpoints: `checkp

