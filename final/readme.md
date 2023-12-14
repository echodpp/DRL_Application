
# AIPI531 Final Project: Evaluation of a Movie Recommendation System

## Team Members
- Echo Chen
- Tianyi Hu
- Jiaxin Ying

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
Absolutely! I'll provide a summary and a table of hit rates for the different recommendation models you've tested. This summary and table can be included in your README file for a clear overview of your project and findings.

