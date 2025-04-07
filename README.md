# EVALUATION OF LLMs FOR TEXT FORMALITY CLASSIFICATION


This project focuses on evaluating large language models (LLMs) on the task of classifying text by formality level. The models were tested on a custom dataset consisting of four distinct formality classes: slang, informal, consultative, and academic.

# Models Tested

- **DeepSeek**
- **LLaMA 2**
- **Mistral**

# Datasets Used

- [breadlicker45/discord_data](https://huggingface.co/datasets/breadlicker45/discord_data) (slang style)

- [li2017dailydialog/daily_dialog](https://huggingface.co/datasets/li2017dailydialog/daily_dialog) (informal style)

- [bigscience-data/roots_en_ted_talks_iwslt](https://huggingface.co/datasets/bigscience-data/roots_en_ted_talks_iwslt) (consultative style)

- [somosnlp-hackathon-2022/scientific_papers_en](https://huggingface.co/datasets/somosnlp-hackathon-2022/scientific_papers_en) (academic style)

# Project structure:

- **dataset_collection.ipynb** — code for building and filtering the dataset by formality levels

- **Evaluation.ipynb** — evaluation notebook for testing different LLMs on the classification task

- **Report.txt** — a short write-up describing the dataset collection process, model behavior, and key observations

# How to Run:

- Use **dataset_collection.ipynb** to generate the balanced dataset 
- Use **Evaluation.ipynb** to run evaluations (requires Hugging Face API keys for model access).


# Notes

- Evaluation metrics include **accuracy**, **precision**, **recall**, **f1-score**, and **confusion matrix**.
- **DeepSeek** demonstrates best overall with minimal prompt tuning.
- **Mistral** showed consistently good performance despite on smaller size 
- **LLaMA 2** showed poor results, even after multiple attempts at prompt tuning — often collapsing different styles into a single class.

# Future work and Limitations

- Current setup mixes dialogue (slang, informal) and monologue (consultative, academic) formats, which may bias the models.

- Many real-world texts contain a blend of styles, which is not captured by strict classification.

- Future versions could reformulate the task as a regression problem (predicting a continuous formality score) or as multi-label classification to reflect mixed stylistic features.