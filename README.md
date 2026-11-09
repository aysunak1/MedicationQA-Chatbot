# MedicationQA Chatbot

A medical question-answering chatbot developed using Natural Language Processing (NLP) and Transformer-based models. This project compares **T5-small** and **FLAN-T5-small** models fine-tuned on the MedicationQA dataset and provides an interactive chatbot interface.

## Project Overview

The aim of this project is to explore transformer-based language models for answering medication-related questions.

Three different approaches are available:

- **T5-small:** Fine-tuned sequence-to-sequence language model.
- **FLAN-T5-small:** Fine-tuned instruction-tuned language model.
- **TF-IDF:** A retrieval-based approach that finds the most similar question in the training dataset and returns its corresponding answer.

Users can select an approach and interact with the chatbot through a Gradio interface.

## Technologies Used

- Python
- Hugging Face Transformers
- Hugging Face Datasets
- T5-small
- FLAN-T5-small
- Scikit-learn
- TF-IDF
- Gradio
- ROUGE
- BLEU
- Google Colab

## Dataset

The project uses the [MedicationQA dataset](https://huggingface.co/datasets/truehealth/medicationqa).

The dataset contains 690 question-answer pairs and was divided into three subsets:

| Dataset | Samples |
|---|---:|
| Training | 552 |
| Validation | 69 |
| Testing | 69 |
| **Total** | **690** |

The data was cleaned before model training by removing empty questions and answers.

## Model Training

Both T5-small and FLAN-T5-small models were fine-tuned using the Hugging Face Transformers library.

Training configuration:

- Epochs: 3
- Learning rate: 2e-4
- Training batch size: 4
- Evaluation batch size: 4
- Maximum input length: 128
- Maximum target length: 128

## Model Evaluation

The models were evaluated on the test dataset using ROUGE and BLEU metrics.

| Model | ROUGE-1 | ROUGE-2 | ROUGE-L | BLEU |
|---|---:|---:|---:|---:|
| T5-small | 0.1065 | 0.0157 | 0.0890 | 0.0000 |
| FLAN-T5-small | 0.0169 | 0.0002 | 0.0157 | 0.0000 |

Based on the ROUGE-L results, T5-small achieved a higher score than FLAN-T5-small in this experiment.

These results reflect the specific dataset, training configuration, and evaluation setup used in this project.

## Chatbot Interface

An interactive chatbot interface was developed using Gradio.

Users can:
- Enter medication-related questions.
- Select between T5-small, FLAN-T5-small, and TF-IDF.
- Receive generated or retrieved answers.

## How to Run

1. Open the `MedicationQA_Final.ipynb` notebook in Google Colab.
2. Select a GPU runtime if available.
3. Run the notebook cells in order.
4. Wait for the dataset preparation and model training processes to complete.
5. Run the final cell to launch the Gradio chatbot interface.

## Project Structure

```text
MedicationQA-Chatbot/
│
├── MedicationQA_Final.ipynb
└── README.md
```
