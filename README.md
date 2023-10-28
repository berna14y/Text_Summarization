# Text Summarization
Text Summarization using BART and TF-IDF

This code demonstrates two different approaches for generating document summaries: extractive and abstractive summarization. 
I'll explain each part of the code in detail.

1) Data Loading:
The code first loads the "cnn_dailymail" dataset using the Hugging Face's datasets library. This dataset contains news articles and their corresponding summaries.
It selects an article from the test split of the dataset.
2) Tokenization and Preprocessing:
The article is tokenized into sentences using NLTK's sent_tokenize method.
Stopwords are removed, and the sentences are preprocessed to remove non-alphanumeric characters and convert them to lowercase.
3) Extractive Summarization:
TF-IDF (Term Frequency-Inverse Document Frequency) features are calculated for the preprocessed sentences. TF-IDF is a technique to determine the importance of words or phrases in a document relative to a collection of documents.
Cosine similarity is computed between sentence TF-IDF vectors to measure their similarity.
Sentence scores are obtained by summing the cosine similarity values for each sentence.
The top N sentences with the highest scores are selected as the extractive summary.
4) Abstractive Summarization:
The code uses the BART model for abstractive summarization. It first tokenizes the document using the BART tokenizer.
The BART model is used to generate a summary for the input document with specific constraints on the summary's length and quality.
5) Hugging Face Transformers Summarization Pipeline:
The code uses the Hugging Face Transformers library's summarization pipeline to generate an abstractive summary. It passes the input document to the pipeline, specifying the desired summary length.

In summary, this code showcases two different approaches for generating document summaries: extractive summarization based on TF-IDF and cosine similarity, and abstractive summarization using the BART model. It also demonstrates how to use the Hugging Face Transformers library to perform abstractive summarization with a pre-trained model.
