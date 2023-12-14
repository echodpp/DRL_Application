
# AIPI531 Final Project: Evaluation of a Movie Recommendation System

## Team Members’ Contribution 

### Echo Chen
* User-Based Collaborative Filtering Model: Generates recommendations based on similarity between users and their movie rating patterns.
* Weighted User-Based Collaborative Filtering Model: An enhancement of the above model that applies weights to different users based on their degree of similarity.
* Most Popular Movie Recommender Baseline Model: A non-personalized baseline model that simply suggests the globally most viewed movies.

### Jiaxin Ying
* Prompt Engineering with GPT-3.5 Model: Employs optimized prompt design to query the GPT-3.5 language model to produce movie recommendations personalized to the user context.
* Zero-Shot Prompting Model: Leverages GPT-3.5's zero-shot generalization capability to generate recommendations without additional fine-tuning on movie data.

### Tianyi Hu
* Few-Shot Prompting Model: Fine-tunes GPT-3.5 on a small set of movie recommendation examples to tailor its prediction capabilities, prior to prompt-based querying.

## Overview

This project is a collaborative effort to develop and evaluate a sophisticated movie recommendation system leveraging the predictive capabilities of Large Language Models (LLMs). The primary objective is to assess the effectiveness of LLMs in generating personalized and relevant movie recommendations, compared to traditional and baseline recommendation models.

### System Description

The recommendation system consists of:

- A LLM (GPT-3.5 and GPT-4) fine-tuned on movie recommendation data.
- An innovative prompt engineering framework designed to effectively query the LLM.
- A traditional User-Based Collaborative Filtering model, enhanced with weighted recommendations.
- A basic popularity-based recommender as a baseline for comparison.
- An evaluation module utilizing hit rate metrics to quantify the recommendation accuracy.

The system operates by analyzing a user's movie watching history, using prompt engineering to formulate contextual recommendation queries for the LLM, and then generating movie suggestions.

### Methodology 

#### Prompt Engineering

The prompt engineering approach involves crafting prompts that provide the LLM with relevant context about a user's interests, based on their watch history. This method was optimized by testing various prompt structures to enhance the accuracy of recommendations.

#### Collaborative Filtering

The project also explores a traditional User-Based Collaborative Filtering approach, including an enhanced version with weighted recommendations. This method relies on user-item interaction patterns to generate suggestions.

#### Evaluation

The evaluation focuses on the 'hit rate' metric, which measures the percentage of correct recommendations out of the total suggestions. This metric is critical for assessing how often each model's recommendations match the user's actual subsequent movie choice.

#### Experiments and Findings:
The project revealed that while traditional methods like User-Based Collaborative Filtering show reasonable accuracy, enhanced methods like weighted recommendations significantly improve the hit rate. However, the most accurate predictions come from advanced AI models, with GPT-4 outperforming GPT-3.5.

### Hit Rate Table

| Model Type                                                 | Hit Rate            | Correct Predictions / Total Users |
|------------------------------------------------------------|---------------------|-----------------------------------|
| Most Popular Movie Recommender (Baseline)                  | 0.1118 (11.18%)     | 19 / 170                          |
| User-Based Collaborative Filtering                         | 0.1588 (15.88%)     | 27 / 170                          |
| User-Based Collaborative Filtering (Weighted Recommendations) | 0.3824 (38.24%)     | 65 / 170                          |
| Prompt Engineering with GPT-3.5                            | 0.4765 (47.65%)     | 81 / 170                          |
| Prompt Engineering with GPT-4                              | 0.5412 (54.12%)     | 92 / 170                          |

### Brief Summary of Findings:
- **Most Popular Movie Recommender**: Served as a basic baseline with the lowest performance.
- **User-Based Collaborative Filtering**: Showed improvement over the baseline.
- **User-Based Collaborative Filtering (Weighted Recommendations)**: Significantly improved the hit rate, demonstrating the value of weighting similar users' preferences.
- **Prompt Engineering with GPT-3.5 and GPT-4**: Advanced AI models performed the best, with GPT-4 leading in accuracy. This highlights the potential of leveraging AI for complex recommendation tasks.

The experiments involved testing various recommendation models:

- **Most Popular Movie Recommender (Baseline)**: Served as a basic comparison standard.
- **User-Based Collaborative Filtering**: Provided reasonable accuracy improvements over the baseline.
- **User-Based Collaborative Filtering (Weighted Recommendations)**: Demonstrated significant improvements in hit rate, validating the effectiveness of weighting similar users' preferences.
- **Prompt Engineering with GPT-3.5 and GPT-4**: These advanced AI models showed superior performance in predicting user preferences, with GPT-4 outperforming GPT-3.5.

### Code and Reproducibility




### Conclusion and Future Work

The project underscores the potential of LLMs, particularly GPT-3.5 and GPT-4, in enhancing the accuracy and personalization of movie recommendations. The findings suggest that combining traditional collaborative methods with advanced AI models could lead to more precise recommendations. Future work could involve integrating additional contextual data, such as movie plots or user demographics, to further refine the recommendation accuracy. This project serves as a valuable proof-of-concept highlighting the applicability of LLMs in recommender systems.

### References and Tools

1.Hugging Face open source LLMs: https://huggingface.co/blog/llama2

2.0penAl LLMs: https://openai.com/chatopt

3.Prompt Engineering: https://www.promptingquide.ai

4.RAG: https://arxiv.org/pdf/2005.11401.pdf

5.Langchain: https://python.langchain.com/docs/get_started/introduction

6.Different ideas for applying LLMs for product recommendations (without fine-tuning):
* https://arxiv.org/pdf/2303.14524.pdf
* https:/larxiv.org/pdf/2305.02182.pdf
* https://arxiv.org/pdf/2304.10149.pdf

