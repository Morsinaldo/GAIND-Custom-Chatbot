# GAIND-Custom-Chatbot

The main objective of this project is to build a customized chatbot capable of answering questions using a customized database. That is, a data set that was not used during model training.

<div align="center">
  <img src="./figures/custom_chatbot.jpg" alt="Category">
  <a href="https://www.freepik.com/free-vector/chatbot-technology-isometric-icons-interface-set_5723560.htm#query=chatbot&position=36&from_view=keyword&track=sph&uuid=10de13a7-88d2-438b-a14c-888cf5f43d12">Image by upklyak</a> on Freepik
</div>

## Rubrics

### 1. Choose a Dataset and Explain the Scenario

In this project, a dataset containing 101 facts about the Premier League for the 2022/23 season was used, coming from the page `theanalyst.com`. This dataset was chosen because we aim to develop a tool that acts as an expert and can provide answers to questions related to this specific league and season.

To improve the question answering capability of our tool, we employ the Retrieval Augmented Generation technique. This technique complements the prompt with contextual information from the dataset, allowing the model to provide more accurate and relevant answers to the questions posed to it.

### 2. Prepare the Dataset for the Custom Query Process

The chosen dataset was loaded into a `pandas` dataframe with a column called "text". This column should contain all of your text data, separated into at least 20 lines. To do this, a web scraping of the page was carried out [101 Best Premier League Facts of the 2022-23 Season](https://theanalyst.com/eu/2023/05/101-best-premier-league-facts-2022-23) and then transformed into a DataFrame so that embeddings could be created in the next step. The objective of this was to demonstrate the correct functioning of the project, since OpenAI's GPT-3.5 has information until 2021.

### 3. Perform the Custom Query Process

To perform the customized query, embeddings were created using the OpenAI API and saved in the `csv` file. With this, a customized search was carried out with an OpenAI `Completion` Model.

### 4. Write Questions to Demonstrate Custom Performance

Para avaliar o resultado do projeto desenvolvido, foram realizadas três querys, cada uma com e sem contexto. Nesta etapa, obteu-se os seguintes resultados:

#### Question 1

**Answer without Context**: It is not possible to accurately answer this question as the 2022/2023 Premier League season has not yet taken place.

**Answer with Context**: Man City won the Premier League in the 2022/2023 season.

#### Question 2

**Answer without Context**: Harry Kane played for Manchester City in the 2022/2023 season.

**Answer with Context**: Harry Kane played for Tottenham Hotspur in the 2022/2023 season.

#### Question 3

**Answer without Context**: I'm sorry, but I would need more information in order to provide a specific answer to your question. Please provide the name of the sport and teams involved in the match.

**Answer with Context**: Liverpool finished the match with the most competitive win, defeating Manchester United 7-0 in March 2024.

### Conclusions

**Question 1**: It is evident that the model correctly responded after querying the custom database, indicating its ability to retrieve relevant information when necessary.
**Question 2**: The model provided an incorrect response to the question when not provided with the context from the custom database. However, upon utilizing the custom database, it furnished a correct response, underscoring the significance of context in response accuracy.
**Question 3**: It is evident that the model correctly responded after querying the custom database, indicating its ability to retrieve relevant information when necessary.

## How to execute

1 - Clone this repositoy

```bash
git clone https://github.com/Morsinaldo/GAIND-Custom-Chatbot.git
cd GAIND-Custom-Chatbot
```

2 - Create the virtual environment

```bash
conda env create -f environment.yml
```

This step uses [Anaconda](https://www.anaconda.com/) as the environment manager, but feel free to use another one of your choice. You also can use `requirements.txt` file to install the necessary libraries.

3 - Run the [notebook](./notebook.ipynb) file.

**Important**: You need to put your OpenAI key in the first cell to run the notebook.

```python
# Environment variables
OPENAI_API_KEY = 'YOUR API KEY'
```

## References

[Generative AI NanoDegree](https://www.udacity.com/enrollment/nd608/1.0.14)