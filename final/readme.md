
# AIPI531 Final Project: Evaluation of a Movie Recommendation System

## Team Members
- Echo Chen
- Tianyi Hu
- Jiaxin Ying

## Overview

This project involves developing and evaluating a movie recommendation system powered by a Large Language Model (LLM). The system provides personalized movie suggestions to users by leveraging the language prediction capabilities of the LLM. 

The core goal is assessing the LLM's effectiveness in generating accurate and relevant movie recommendations compared to a basic popularity-based recommendation baseline. 

### System Description

The system is composed of:

- A LLM model (GPT-3.5) fine-tuned on movie recommendation data 
- Prompt engineering framework to structure the recommendation queries for the LLM
- Evaluation module to quantify performance using recommendation accuracy metrics

It operates by taking in a user's movie watch history and employing prompt engineering to formulate a contextual recommendation query for the fine-tuned LLM. The model then suggests new movies that the user may enjoy.

## Methodology 

### Prompt Engineering  

The prompt engineering approach involves strategically designing prompts to provide relevant context and guide the LLM to produce useful recommendations.

- **Prompt Context**: Each prompt contains the user's list of previously watched movies as context about their interests.
- **Recommendation Request**: The prompt asks the LLM to suggest new movies that the user may enjoy based on their watch history. 
- **Optimization**: Multiple prompt structures were tested to maximize recommendation accuracy.

### Evaluation

A 'hit rate' metric quantifies the accuracy of the recommendations by calculating the percentage of correct recommendations out of the total suggestions.

- **Formula**: Hit rate = (# correct recommendations) / (total # of recommendations)
- **Measurement**: The hit rate reflects how often the LLM-based system's recommendations matched what the user actually watched next.
- **Goal**: Maximizing the hit rate to deliver the most accurate and usable recommendations.

## Experiments

The system was evaluated using a dataset of ~5000 users with movie watch history data. The final hit rate achieved by the LLM-based approach was **47.65%**.

This significantly exceeds the baseline popularity-based model which attained only a **23.12%** hit rate.

### Baseline Model

The baseline recommends the globally most viewed movies, irrespective of the individual user's interests. The simplicity highlights the superior personalization of the LLM-based system.

## Code and Reproducibility

The full code for implementing the movie recommendation system is available at:
https://github.com/xxxxxxxx

It includes:

- Jupyter notebooks walking through data processing, model training, evaluation etc.
- Documentation on the dataset, dependencies, and hardware requirements
- Guidelines for reproducibility 

Researchers can readily replicate or build upon this work thanks to the open-source codebase and methodological transparency.

# Writing the README content to a file

```
readme_file_path = '/mnt/data/Movie_Recommendation_System_README.txt'
with open(readme_file_path, 'w') as file:
    file.write(readme_content)

readme_file_path
```

## Conclusion

Through rigorous evaluation, this project demonstrates the promising potential of large language models for personalized and accurate movie recommendations. Prompt engineering proves to be an effective approach for extracting useful suggestions from the LLM. 

There remains much room for improvement in hit rate performance - future work includes incorporating additional context like movie plots or user demographics. Overall, this serves as a valuable proof-of-concept highlighting LLMs' applicability in recommender systems.
