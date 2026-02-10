[![Review Assignment Due Date](https://classroom.github.com/assets/deadline-readme-button-24ddc0f5d75046c5622901739e7c5dd533143b0c8e959d652212380cedb1ea36.svg)](https://classroom.github.com/a/bV_AQ86u)
# Text TO SQL

## Environment

Virtual environment creation using conda:
```
conda create -n hw4-part-2-nlp python=3.10
conda activate hw4-part-2-nlp
python -m pip install -r requirements.txt
```

## Evaluation commands

If you have saved predicted SQL queries and associated database records, you can compute F1 scores using:
```
python evaluate.py
  --predicted_sql results/t5_ft_dev.sql
  --predicted_records records/t5_ft_dev.pkl
  --development_sql data/dev.sql
  --development_records records/ground_truth_dev.pkl
```

## Testing

For SQL queries, ensure that the name of the submission files (in the `results/` subfolder) are:
- `{t5_ft, ft_scr, gemma}_test.sql`

For database records, ensure that the name of the submission files (in the `records/` subfolder) are:
- `{t5_ft, ft_scr, gemma}_test.pkl`


