# ROCK: A Causal Inference Framework for Reasoning About Commonsense Causality

This repo contains official code for the paper "ROCK: A Causal Inference Framework for Reasoning About Commonsense Causality".



# Reproducing Experiments
## Dependencies
 
 We use Python 3.8 and ``pytorch`` for training neural nets, please use 
 ``pip install -r requirements.txt`` (potentially in
 a virtual environment) to install dependencies.

## Notebook Overview

  - `result_presentation.ipynb`: use this notebook to reproduce all figures and tables in the paper.
  - `causal_reasoner.ipynb`: use this notebook to estimate $\hat{\Delta}_p$. Instructions on extending ROCK is also included there.
  - `nyt_finetune.ipynb`: use this notebook for temporality fine-tuning using NYT corpus.

## Datasets and Pre-Computed Results
  Some operations are computationally heavy (e.g., GPT-J model requires 25GB memory),
  you can download our pre-computed results using *anonymous* Dropbox links below:
  - [`exp_data.zip` (155M)](https://www.dropbox.com/s/9egrzn1ny3oq2qa/roberta_ft.tar.gz?dl=1): This is used by the `result_presentation`; the `causal_reasoner` can generate some of the processed data in this archive.
  - [`roberta_ft.tar.gz` (1.29G)](https://www.dropbox.com/s/9egrzn1ny3oq2qa/roberta_ft.tar.gz?dl=1): This is the fine-tuned RoBERTa model we used in our paper as the temporality predictor. This can be generated from `nyt_finetune` notebook and is used by `causal_reasoner` notebook.
  - [`nyt_ft.zip` (9M)](https://www.dropbox.com/s/1kigmy4wj41vw14/nyt_ft.zip?dl=0): This is the fine-tuning dataset we used, obtained from SRL on the [original NYT corpus](https://catalog.ldc.upenn.edu/LDC2008T19).
## Code Structure
  
  After installing the dependencies and download all components, the repo structure should look as:

```
.
├── LICENSE                         # code license
├── README.md                       # this file
├── causal_reasoner.ipynb
├── nyt_finetune.ipynb
├── result_presentation.ipynb
├── models
│   └── roberta_ft
│       └── ... (omitted)
├── exp_data
│   ├── acc_N_res.csv
│   ├── acc_noft_res_full.csv
│   ├── acc_res_full.csv
│   ├── copa_dev.json
│   ├── copa_dev_probs.csv
│   ├── copa_dev_probs_noft.csv
│   ├── copa_test.json
│   ├── copa_test_probs.csv
│   ├── copa_test_probs_noft.csv
│   ├── glucose_d1_probs.csv
│   ├── glucose_d1_probs_noft.csv
│   └── nyt_fine_tune.csv
└── src
    ├── metric_utils.py
    ├── metrics.py
    ├── pipeline.py
    ├── plotter.py
    ├── train_finetune.py
    └── utils.py
```


