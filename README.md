# CSE584Mid README TEMPLATE

# LLM Attribution Classifier Project

## Project Overview

This project aims to build a deep learning classifier to attribute text completions to different Large Language Models (LLMs). Given a set of incomplete texts (e.g., "Yesterday I went"), each LLM generates a continuation, resulting in different completions. The classifier is trained to identify which LLM generated the continuation for each `(xi, xj)` pair.

## Table of Contents

- [Project Overview](#project-overview)
- [Dataset](#dataset)
- [Modeling Approach](#modeling-approach)
- [Installation](#installation)
- [Usage](#usage)
  - [Data Preprocessing](#data-preprocessing)
  - [Training the Classifier](#training-the-classifier)
  - [Evaluating the Classifier](#evaluating-the-classifier)
  - [Generating New Completions](#generating-new-completions)
- [Experiments and Results](#experiments-and-results)
- [Contributors](#contributors)
- [License](#license)

## Dataset

The dataset consists of pairs of truncated and completed texts `(xi, xj)`, where:
- **xi**: The initial incomplete text prompt (e.g., "Yesterday I went").
- **xj**: The continuation generated by one of the six LLMs.
- **llm**: The label identifying which LLM produced the completion.

### Data Structure
The dataset is organized as a CSV file with the following columns:

| Column | Description                                   |
|--------|-----------------------------------------------|
| xi     | Truncated 3-word text prompt                         |
| xj     | Completion generated by an LLM                |
| llm    | Label identifying the LLM (class label)       |

## Modeling Approach

We utilize various deep learning classifiers to attribute completions to the correct LLM. The classifiers explored include:
- Transformer-based models (BERT, RoBERTa, T5, etc.)
- Recurrent Neural Networks (LSTM, GRU)
- Traditional machine learning methods
- Ensemble models to combine multiple architectures

Our experiments compare the accuracy of these models in attributing completions to the correct LLM and identify the best-performing architecture.

## Usage

1. Clone the repository:
    ```bash
    git clone https://github.com/MingZhu5281/CSE584Mid.git
    cd CSE584Mid
    ```

2. Run the training code to get the results and save the model:
    ```bash
    python BERT_optimized.py
    ```
