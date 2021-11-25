This study used the following Python Notebooks:
1. Aylien_Covid19_News_Dataset_Extraction.ipynb
2. Covid19_Econ_Impact_Topics.ipynb
3. Topics_Cosine_Similarity.ipynb


1. Aylien_Covid19_News_Dataset_Extraction.ipynb:

This notebook is used to extract the required fields from the "aylien_covid_news_data.jsonl" source data file. The output is saved as a csv file. 
Only requirement to run this script on another PC is to replace the file_path variable with the filepath to the jsonl file.
Input: "aylien_covid_news_data.jsonl"
Output: "AylienCovid19.csv"


2. Covid19_Econ_Impact_Topics.ipynb:

The main purpose of this notebook is to optimise and train the LDA models for each of the countries and obtain the metrics for evaluation. 
It also visualises the number of topics vs. coherence scores, the LDA model intertopic distances, and the LDA model top words. 
The visualisation, topic model results, and trained models for each country is saved.
Only requirement to run this script on another PC is to change the file path to point to the AylienCovid19.csv file.
Input: "AylienCovid19.csv" --> this is the output saved from the Aylien_Covid19_News_Dataset_Extraction.ipynb notebook.
Outputs:
- country_k.csv --> number of topic optimisation results for each country (e.g. US_k.csv)
- country_Topics_K.png --> visual of topic optimisation results for each country (e.g. US_Topic_K.png)
- model_country.model --> trained LDA model for each country (e.g. model_US.model)
- country_Topics.csv --> top 20 words from each topic for each country (e.g. US_Topic.csv)


3. Topics_Cosine_Similarity.ipynb:

This notebook performs cosine similarity on the top 20 words for each topic extracted for each country and outputs a heatmap of the cosine similarity scores for each country pair.
Only requirement to run this script on another PC is to replace the filepath variable with the filepath to the folder containing the labeled country topic csv files (Refer to src folder).
Input: country_Topics_Labeled.csv for each country (see src folder)
Output: country1_country2_Sim.png for each country pair (e.g. US_IN_Sim.png)
