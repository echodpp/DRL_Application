
# AIPI531 Final Project: Evaluation of a Movie Recommendation System

## Team Members’ Contribution 

#### Echo Chen
* Most Popular and User-Based Collaborative Filtering baseline Model
* Initial Prompt Engineering, try few-shot Prompt Engineering

#### Jiaxin Ying
* Whole Prompt Engineering process with GPT-3 Model

#### Tianyi Hu
* Evaluate different Prompt Engineering techniques, test GPT-4 Model

## Overview

This project is a collaborative effort to develop and evaluate a sophisticated movie recommendation system leveraging the predictive capabilities of Large Language Models (LLMs). The primary objective is to:
1. assess the effectiveness of LLM-based approaches in generating personalized and relevant movie recommendations 
2. compare LLM approaches with traditional and baseline recommendation models.
3. evaluate the performace of LLMs with different prompt engineering techniques.

### System Description

The recommendation system project consists of:

- A basic popularity-based recommender as a baseline for comparison.
- A traditional User-Based Collaborative Filtering model, enhanced with weighted recommendations.
- LLM-based (GPT-3 and GPT-4) approaches for movie recommendation.
- Different prompt engineering frameworks designed to effectively query the LLM.
- An evaluation module utilizing hit rate metrics to quantify the recommendation accuracies for above methods.

The system operates by analyzing a user's movie-watching history, using prompt engineering to formulate contextual recommendation queries for the LLM, and then generating movie suggestions.

### Methodology 


In our project, we employed LLMs (GPT-3 and GPT-4) with prompt engineering, focusing on a structured, multi-step process tailored to enhance the accuracy and relevance of movie recommendations. This approach combines Chain-of-Thought Prompting, Zero-shot Prompting, and Directional Stimulus Prompting.

#### Techniques and Approaches
1. **Popularity-based** Recommender

2. **Collaborative-filtering-based** Recommender
    The project also explores a traditional User-Based Collaborative Filtering approach, including an enhanced version with weighted recommendations. This method relies on user-item interaction patterns to generate suggestions.

3. **LLM-based** Recommender with **different number of steps**:
    1. **2-step** Prompt Engineering (prompt_1 and prompt_2 templates):
       - **Step 1**: Here, the model is prompted to provide a more detailed analysis by summarizing the style and main actors of each watched movie. This step offers specific attributes for each movie, rather than a general summary of preferences, and is more aligned with **Directional Stimulus Prompting**, where the prompt directs the AI's focus to specific movie attributes.
       - **Step 2**: Building on the detailed attributes from Step 1, the model is tasked with recommending movies from a candidate set that share similar styles and actors with the movies the user has watched. This approach is targeted, using distinct movie characteristics to guide the recommendations.

    2. **3-step** Prompt Engineering (temp_1, temp_2, and temp_3 templates):
       - **Step 1**: The model is prompted to summarize the user's preferences based on the movies they have watched. This step aims to identify key features the user might value in movies, such as genres, themes, or actors. This aligns with aspects of **Chain-of-Thought Prompting**, guiding the model through a logical process of deriving user preferences.
       - **Step 2**: The model is then requested to select movies from the user's watch history that align with these summarized preferences. This step focuses on pinpointing specific movies that reflect the user's tastes, utilizing a form of **Zero-shot Prompting** where the model uses its inherent knowledge to make selections.
       - **Step 3**:

3. **LLM-based** Recommender with **different prompt enigneering tricks**:

#### Summary

Our methodology in prompt engineering reflects a creative application of established techniques adapted to the specific requirements of our movie recommendation task. By guiding LLM through a structured, multi-step reasoning process and focusing on both general user preferences and specific movie attributes, we have developed a system that effectively leverages the AI's capabilities for personalized recommendations. This approach demonstrates the potential of combining different prompt engineering strategies to optimize the performance of language models in complex tasks such as movie recommendations.




#### Evaluation

The evaluation focuses on the 'hit rate' metric, which measures the percentage of correct recommendations out of the total suggestions. This metric is critical for assessing how often each model's recommendations match the user's actual subsequent movie choice.

#### Experiments and Findings:
The project revealed that while traditional methods like User-Based Collaborative Filtering show reasonable accuracy, enhanced methods like weighted recommendations significantly improve the hit rate. However, the most accurate predictions come from advanced AI models, with GPT-4 outperforming GPT-3.5.

### Hit Rate Table

| Model Type                                                 | Hit Rate            | Correct Predictions <br> / Total Users |
|------------------------------------------------------------|---------------------|-----------------------------------|
| Popularity-based <br> Movie Recommender (Baseline)                  | 0.1118 (11.18%)     | 19 / 170  |
| User-Based <br> Collaborative Filtering                         | 0.1588 (15.88%)     | 27 / 170   |
| User-Based <br> Collaborative Filtering <br> (Weighted Recommendations) | 0.3824 (38.24%)     | 65 / 170 |
| LLM-based <br> (GPT-3.5)                            | 0.4765 (47.65%)     | 81 / 170        |
| LLM-based <br> (GPT-4)                              | 0.5412 (54.12%)     | 92 / 170       |

### Brief Summary of Findings:
- **Most Popular Movie Recommender**: Served as a basic baseline with the lowest performance.
- **User-Based Collaborative Filtering**: Showed improvement over the baseline.
- **User-Based Collaborative Filtering (Weighted Recommendations)**: Significantly improved the hit rate, demonstrating the value of weighting similar users' preferences.
- **Prompt Engineering with GPT-3, GPT-3.5 and GPT-4**: Advanced AI models performed the best, with GPT-4 leading in accuracy. This highlights the potential of leveraging AI for complex recommendation tasks.

The experiments involved testing various recommendation models:

- **Most Popular Movie Recommender (Baseline)**: Served as a basic comparison standard.
- **User-Based Collaborative Filtering**: Provided reasonable accuracy improvements over the baseline.
- **User-Based Collaborative Filtering (Weighted Recommendations)**: Demonstrated significant improvements in hit rate, validating the effectiveness of weighting similar users' preferences.
- **Prompt Engineering with GPT-3.5 and GPT-4**: These advanced AI models showed superior performance in predicting user preferences, with GPT-4 outperforming GPT-3.5.

### Code and Reproducibility
The implementation of our movie recommendation system is organized across several Jupyter notebooks hosted on Google Colab for ease of access and execution. Below is an overview of these notebooks and instructions for their use:

1. **Baseline Models (`baseline.ipynb`):**
   - This notebook contains the implementation of three baseline recommender systems:
     - Most Popular Movie Recommender
     - User-Based Collaborative Filtering
     - User-Based Collaborative Filtering with Weighted Recommendations
   - **Data Requirement**: Make sure to have the `movieslen_100k` dataset correctly placed in the defined directory. you can also find it in our repo under `data/` directory. 

2. **GPT-3.5 and GPT-4 Models (`gpt3.ipynb` and `gpt4.ipynb`):**
   - Separate notebooks are provided for the GPT-3.5 and GPT-4-based recommendation systems.
   - **Data and API Key Requirement**: Make sure to have the `movieslen_100k` dataset correctly placed in the defined directory. Additionally, an OpenAI API key is necessary to connect to the respective LLMs (GPT-3.5 and GPT-4). Insert your API key in the designated section of the notebooks.

### Conclusion and Future Work

The project underscores the potential of LLMs, particularly GPT-3.5 and GPT-4, in enhancing the accuracy and personalization of movie recommendations. The findings suggest that combining traditional collaborative methods with advanced AI models could lead to more precise recommendations. Future work could involve integrating additional contextual data, such as movie plots or user demographics, to refine the recommendation accuracy further. This project serves as a valuable proof-of-concept highlighting the applicability of LLMs in recommender systems.

### References and Tools

1.0penAl LLMs: https://openai.com/chatopt

2.Prompt Engineering: https://www.promptingquide.ai

3.Langchain: https://python.langchain.com/docs/get_started/introduction

4.Different ideas for applying LLMs for product recommendations (without fine-tuning):
* https://arxiv.org/pdf/2303.14524.pdf
* https://arxiv.org/pdf/2305.02182.pdf
* https://arxiv.org/pdf/2304.10149.pdf

