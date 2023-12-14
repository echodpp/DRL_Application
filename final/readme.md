
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
3. compare LLM approaches with different models.
3. evaluate the performace of LLMs with different prompt engineering techniques.

### System Description

The recommendation system project consists of:

- A basic popularity-based recommender as a baseline for comparison.
- A traditional User-Based Collaborative Filtering model, enhanced with weighted recommendations.
- LLM-based (GPT-3, GPT-3.5 and GPT-4) approaches for movie recommendation.
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
       - **Step 3**: Based on the questions and answers of both the Step1 and Step2, the model is asked to recommend 10 movies from a candidate set that is similiar to the selected moives the user had watched.

3. **LLM-based** Recommender with **different prompt enigneering tricks**:
	We implement and evaluate the performance of the 2-step-prompt-based approaches but with different popular prompt engineering tricks, such as adding "You are an expert in movie recommendation" and "Let's think step by step".  	



### Evaluation

The evaluation focuses on the 'hit rate' metric, which measures the percentage of correct recommendations out of the total suggestions. This metric is critical for assessing how often each model's recommendations match the user's actual subsequent movie choice.

##### Evaluation Metric: Hit Rate
In this project we evaluate the recommendation performance using the metric hit rate @ k (HR@k).
A hit in HR@k means the ground truth selection of the user appears in the $k$ recommendations given by the model in each recommendation round.
HR@k then calculates the average percentage of hit in all rounds.
In this work, we use HR@10, which evluate the average percentage of hit when the model provides 10 potential movies for recommendation.



##### Table1. Recommendation Performace (Hit Rate@10) Comparison <br> - Tradictional methods V.S. LLM-based methods

| Model Type                                                 | Hit Rate            | Correct Predictions <br> / Total Users |
|------------------------------------------------------------|---------------------|-----------------------------------|
| Popularity-based <br> Movie Recommender (Baseline)                  | 0.1118 (11.18%)     | 19 / 170  |
| User-Based <br> Collaborative Filtering                         | 0.1588 (15.88%)     | 27 / 170   |
| User-Based <br> Collaborative Filtering <br> (Weighted Recommendations) | 0.3824 (38.24%)     | 65 / 170 |
| LLM-based <br> (GPT-3: text-davinci-003)                              | 0.5882 (58.82%)     | 100 / 170       |

##### Table2. Recommendation Performace (Hit Rate@10) Comparison <br> - LLM-based methods with different models

| Model Type                                                 | Hit Rate            | Correct Predictions <br> / Total Users |
|------------------------------------------------------------|---------------------|-----------------------------------|
| LLM-based <br> (GPT-3: text-davinci-003)                              | 0.5882 (58.82%)     | 100 / 170       |
| LLM-based <br> (GPT-3.5-Turbo)                            | 0.4765 (47.65%)     | 81 / 170        |
| LLM-based <br> (GPT-4)                              | 0.5412 (54.12%)     | 92 / 170       |


##### Table3. Recommendation Performace (Hit Rate@10) Comparison <br> - LLM-based methods with different promt steps

| Model Type                                                 | Hit Rate            | Correct Predictions <br> / Total Users |
|------------------------------------------------------------|---------------------|-----------------------------------|
| 2step-based <br> (GPT-3: text-davinci-003)                              | 0.5882 (58.82%)     | 100 / 170       |
| 3step-based <br> (GPT-3: text-davinci-003)                            | 0.6294 (62.94%)     | 107 / 170        |



##### Table4. Recommendation Performace (Hit Rate@10) Comparison <br> - LLM-based methods with different promt tricks

| Model Type                                                 | Hit Rate            | Correct Predictions <br> / Total Users |
|------------------------------------------------------------|---------------------|-----------------------------------|
| **Without prompt tricks** <br> ("Think step by step" <br> "You are an expert in <br> movie recommendation") <br> (GPT-3: text-davinci-003)                              | 0.5941 (59.41%)     | 101 / 170       |
| **With prompt tricks** <br> ("Think step by step" <br> "You are an expert in <br> movie recommendation") <br> (GPT-3: text-davinci-003)                            | 0.5647 (56.47%)     | 96 / 170        |

### Brief Summary of Observations:

- Table1 shows the performance comparisons between the tradictional approaches and LLM-based methods.
    - **Most Popular Movie Recommender**: Serves as a basic baseline with the lowest performance.
    - **User-Based Collaborative Filtering**: Show slightly improve over the baseline.
    - **User-Based Collaborative Filtering (Weighted Recommendations)**: Significantly improve the hit rate, demonstrating the value of weighting similar users' preferences.
    - **LLM-based Recommendation**: Advanced AI models (GPT-3) performed the best compared with the traditional method. This highlights the potential of leveraging AI for complex recommendation tasks.

- Table2 shows the performance comparisons between the LLM-based methods with different models
	- To our superise, the **GPT-3 model** performa the best with a HR@10 of 58.82%, while the  **GPT-3-turbo model** and **GPT-4 model** achieve 47.65% and 54.12% respectively.
	- The result shows that higher version of the LLM might not provide an improvement in the performance of recommendation.
	- We also find that [discussions on OpenAI forum](https://community.openai.com/t/gpt-3-5-turbo-vs-text-davinci-003-chatbot/82806)  also show that GPT-3 might outperform GPT-3.5-turbo in some specific task.

- Table3 shows the performance comparisons between the LLM-based methods with different prompt steps.
	- As expected, the 3-step prompt achieves a HR@10 of 62.94%, better than that of the 2-step prompt (58.82%).
	- However, the 3-step prompt also requires much more computation cost and introduce more latency compared with the 2-step prompt as it have to perform more interact with the LLM than the 2-step approach.

- Table 4 shows the performance comparisons between the LLM-based methods with different prompt engineering tricks.
	- To our surprises, adding some popular tricks, such as "You are an expert in movie recommendation" and "Let's think step by step", does not yield a better performance. Without the tricks we achieve HR@10 of 59.41% while adding the tricks the HR@10 drops to 56.47%.
	- It might be because the LLM find it hard to understand what is an expert in movie recommendation as there is not much description of "movie recommendation expert" in literatures while there is much more description of other roles like "teacher", "judge" in its training set.

### Summary

Our methodology in prompt engineering reflects a creative application of established techniques adapted to the specific requirements of our movie recommendation task. By guiding LLM through a structured, multi-step reasoning process and focusing on both general user preferences and specific movie attributes, we have developed a system that effectively leverages the AI's capabilities for personalized recommendations. This approach demonstrates the potential of combining different prompt engineering strategies to optimize the performance of language models in complex tasks such as movie recommendations.

## Conclusion and Future Work

The project underscores the potential of LLMs, particularly GPT-3, GPT-3.5 and GPT-4, in enhancing the accuracy and personalization of movie recommendations. The findings suggest that combining traditional collaborative methods with advanced AI models could lead to more precise recommendations.

Future work could involve integrating additional contextual data as side information, such as movie plots, user demographics, and user ratings, to refine the recommendation accuracy further. This project serves as a valuable proof-of-concept highlighting the applicability of LLMs in recommender systems.

## Code and Reproducibility
The implementation of our movie recommendation system is organized across several Jupyter notebooks hosted on Google Colab for ease of access and execution. Below is an overview of these notebooks and instructions for their use:

1. **Baseline Models (`baseline.ipynb`):**
   - This notebook contains the implementation of three baseline recommender systems:
     - **Most Popular** Movie Recommender
     - **User-Based Collaborative Filtering**
     - **User-Based Collaborative Filtering** with **Weighted Recommendations**
   - **Data Requirement**: Make sure to have the `movieslen_100k` dataset correctly placed in the defined directory. you can also find it in our repo under `data/` directory. 

2. **GPT-3.5 and GPT-4 Models (`gpt3.5.ipynb` and `gpt4.ipynb`):**
   - Separate notebooks are provided for the **GPT-3.5-based** and **GPT-4-based** recommendation systems.
   - **Data and API Key Requirement**: Make sure to have the `movieslen_100k` dataset correctly placed in the defined directory. Additionally, an OpenAI API key is necessary to connect to the respective LLMs (GPT-3.5 and GPT-4). Insert your API key in the designated section of the notebooks.

3. ** 2-step and 3-step prompt (`gpt3_2step.ipynb` and `gpt3_3step.ipynb`):**
   - Separate notebooks are provided for the **2-step prompt** and **3-step prompt** recommendation systems.
   - **Data and API Key Requirement**: Make sure to have the `movieslen_100k` dataset correctly placed in the defined directory. Additionally, an OpenAI API key is necessary to connect to the respective LLMs (GPT-3.5 and GPT-4). Insert your API key in the designated section of the notebooks.

4. ** prompt engineering tricks(`gpt3_prompt_engineering.ipynb`):**
   - A single notebook is provided for the 2-step prompt  recommendation systems ** with different prompt engineering tricks**.
   - **Data and API Key Requirement**: Make sure to have the `movieslen_100k` dataset correctly placed in the defined directory. Additionally, an OpenAI API key is necessary to connect to the respective LLMs (GPT-3.5 and GPT-4). Insert your API key in the designated section of the notebooks.


### References and Tools

1.0penAl LLMs: https://openai.com/chatopt

2.Prompt Engineering: https://www.promptingquide.ai

3.Langchain: https://python.langchain.com/docs/get_started/introduction

4.Different ideas for applying LLMs for product recommendations (without fine-tuning):
* https://arxiv.org/pdf/2303.14524.pdf
* https://arxiv.org/pdf/2305.02182.pdf
* https://arxiv.org/pdf/2304.10149.pdf
* https://arxiv.org/pdf/2205.11916.pdf

