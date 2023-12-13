
# AIPI531 Final Project: Evaluation of a Movie Recommendation System

## Team Members
- Echo Chen
- Tianyi Hu
- Jiaxin Ying

## Project Overview
This comprehensive document presents our team's efforts in evaluating an advanced movie recommendation system. Utilizing Large Language Model (LLM) technology, specifically through prompt engineering techniques, we aimed to investigate the system's efficacy in suggesting movies. Our primary objective was to compare the performance of this LLM-based system against a traditional baseline recommendation model.

## Detailed Prompt Engineering Methodology
- **Approach Description**: We employed a systematic approach to prompt engineering, focusing on creating structured and context-rich prompts. These prompts are designed to navigate the LLM towards more precise movie recommendations.
- **Implementation Details**: Each prompt included a blend of user-specific data, such as lists of previously watched movies, and a set of potential movie recommendations. This approach aimed to simulate a realistic scenario where the LLM would generate suggestions based on the provided context.
- **Prompt Design Strategy**: We meticulously crafted the prompts to enhance both the relevance and accuracy of the LLM's recommendations. This involved iterative testing and refinement of prompt structures.

## In-Depth Evaluation of LLM for Movie Recommendations
- **Evaluation Metric Explained**: We measured the LLM's performance using a 'hit rate' metric. This metric represents the proportion of accurate recommendations made by the system.
- **Quantitative Results**: Our final analysis revealed a hit rate of approximately 47.65% for the GPT-3.5 based system, indicating nearly half of the LLM's recommendations aligned with the users' actual movie preferences.

## Baseline Model for Comparative Analysis
- **Model Overview**: As a point of comparison, we utilized a basic 'most popular' movie recommendation algorithm. This model suggests movies based solely on their popularity, determined by viewing frequencies in our dataset.
- **Evaluation Approach**: Similar to the LLM system, the baseline model's effectiveness was also assessed using the hit rate metric.

## Accuracy Assessment Methods
- **LLM System**: We calculated the LLM's hit rate by dividing the number of accurate predictions by the total predictions made.
- **Baseline Model**: The baseline model's accuracy was similarly evaluated, focusing on the proportion of successful recommendations.

## Rigorous Experimentation Process
- **Data Consistency Assurance**: To ensure a level playing field, both the LLM-based system and the baseline model were tested using an identical user data set.
- **Fairness in Comparison**: We employed the same hit rate metric to evaluate both models, providing a direct and equitable comparison of their performances.

# Writing the README content to a file
,,,
readme_file_path = '/mnt/data/Movie_Recommendation_System_README.txt'
with open(readme_file_path, 'w') as file:
    file.write(readme_content)

readme_file_path
,,,

## Conclusive Remarks
The results of our project indicate a significant superiority of the LLM-based recommendation system over the conventional 'most popular' model. This success highlights the promising potential of advanced language models in crafting personalized and effective recommendation systems.
