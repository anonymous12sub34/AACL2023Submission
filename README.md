# Code for the AACL 2023 Submission - 'Permutation Based Pre-training Strategies for Procedural Text'

## Required dependencies

Please run ```pip install -r requirements.txt```. 

## Hyperparameters for commands
- EMBEDDING_TYPE: Type of embedding ('hamming', 'kenny', 'lehmer'). 
- MODEL_NAME: Name of the base transformer model/HuggingFace model name ('bert', 'roberta').
- MODEL_PATH: Path to the base transformer model ('bert-base-uncased', 'roberta-base').
- RECIPES_STEPS: Number of steps of recipes, or text about any process, in the training data. 
- TEST: Set 'True' to test code on your local machine ('True', 'False'). 
- TOTAL_NUM_PERMUTATIONS: Size of the permutation set. 

## Pretraining using Permutation Classification

Store your data as a list of recipes with each recipe in turn as a list of steps in a pickle file called ```full_corpus.pickle```. Run ```python3 classification.py <MODEL_NAME> <MODEL_PATH> <RECIPES_STEPS> <TEST> <TOTAL_NUM_PERMUTATIONS>```

## Pretraining using Embedding Regression

Run ```python3 embedding.py <EMBEDDING_TYPE> <MODEL_NAME> <MODEL_PATH> <RECIPES_STEPS> <TEST> <TOTAL_NUM_PERMUTATIONS>```

## Fine-tuning on SQuAD 2.0
- To download the training set, run ```wget https://rajpurkar.github.io/SQuAD-explorer/dataset/train-v2.0.json```.
- Run ```python3 finetune_squad.py <MODEL_TYPE> <MODEL_PATH>```. 
- To get the models fine-tuned on SQuAD 2.0, follow the following format to get the link - https://huggingface.co/AnonymousSub/<SUBSTRING AFTER THE LAST '/' IN PRE-TRAINED MODEL LINK>_squad2.0

## Links to Pre-trained models  Fine-tuned on SQuAD 2.0

- Permutation Classification
1. [pc-6-2-roberta_squad2.0](https://huggingface.co/amazonqa1029/pc-6-2-roberta_squad2.0)
2. [pc-6-50-roberta_squad2.0](https://huggingface.co/amazonqa1029/pc-6-50-roberta_squad2.0)
3. [pc-6-200-roberta_squad2.0](https://huggingface.co/amazonqa1029/pc-6-200-roberta_squad2.0)
- Embedding Regression
1. [embeddings-lehmer-6-50-roberta_squad2.0](https://huggingface.co/amazonqa1029/embeddings-lehmer-6-50-roberta_squad2.0)
2. [embeddings-hamming-6-50-roberta_squad2.0](https://huggingface.co/amazonqa1029/embeddings-hamming-6-50-roberta_squad2.0)
3. [embeddings-hamming-6-100-roberta_squad2.0](https://huggingface.co/amazonqa1029/embeddings-hamming-6-100-roberta_squad2.0)
- Skip-Clip
1. [skipclip-4-4-roberta_squad2.0](https://huggingface.co/amazonqa1029/skipclip-4-4-roberta_squad2.0)
