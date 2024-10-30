
# Virology and Epidemiology AI Research Collection

This repository contains the dataset `collection_with_abstracts.csv`, compiled via queries issued to the PubMed database. PubMed is one of the largest databases indexing publications in the Life Sciences.

## 🔬 Dataset Scope

This dataset includes papers from PubMed that address problems in virology or epidemiology using deep learning neural network-based solutions. The dataset consists of **11,450 unique papers**. For more detailed insights into the queries used to compile this collection, please view the queries section below.

## 📑 Data Columns Description

Each row in the `collection_with_abstracts.csv` file corresponds to a unique academic paper, structured with the following columns:

- **PMID**: PubMed ID, a unique identifier for each publication.
- **Title**: Title of the publication.
- **Authors**: List of authors in the format Last Name, First Initials.
- **Citation**: Citation details, typically including volume, issue, and pages.
- **First Author**: The first listed author of the paper.
- **Journal/Book**: The name of the journal or book in which the paper is published.
- **Publication Year**: The year the paper was published.
- **Create Date**: The date the record was created in PubMed.
- **PMCID**: PubMed Central ID, linking to the full text of the article in the PubMed Central database. This field is optional and may not be present for all records.
- **NIHMS ID**: NIH Manuscript Submission ID, used when a paper is included in NIH public access policy compliance. This field is optional and may not be present for all records.
- **DOI**: Digital Object Identifier, providing a persistent link to its location on the internet. This field is optional and may not be present for all records.
- **Abstract**: The abstract of the publication. This field is optional and may not be present for all records.

## ❗ Note on Optional Fields

Fields marked as "optional" may not be present for all records within the dataset. This indicates that certain information is not available or applicable for those specific entries.

## 🌐 Accessing Full Texts

The PubMed Central (PMC) database, a subset of PubMed records, provides access to the full text of articles in XML format or other formats. Articles can be accessed via the API using the following URL: 

Replace `[insert-pmcid-here]` with the actual PMCID of the article.

## 📝 Queries Used

Below are the specific queries issued for the compilation of this dataset:

1. **Virology & Neural Networks**
   - Query: `(((virology) OR (epidemiology)) AND (("neural network") OR ("artificial neural network") OR ("machine learning model") OR ("feedforward neural network") OR ("neural net algorithm") OR ("multilayer perceptron") OR ("convolutional neural network") OR ("recurrent neural network") OR ("long short-term memory network") OR ("CNN") OR ("GRNN") OR ("RNN") OR ("LSTM")))`
   - Results: 3,791

2. **Virology & Deep Learning**
   - Query: `(((virology) OR (epidemiology)) AND (("deep learning") OR ("deep neural networks")))`
   - Results: 2,664

3. **Virology & Computer Vision**
   - Query: `(((virology) OR (epidemiology)) AND (("computer vision") OR ("vision model") OR ("image processing") OR ("vision algorithms") OR ("computer graphics and vision") OR ("object recognition") OR ("scene understanding")))`
   - Results: 3,647

4. **Virology & Natural Language Processing**
   - Query: `(((virology) OR (epidemiology)) AND (("natural language processing") OR ("text mining") OR (NLP) OR ("computational linguistics") OR ("language processing") OR ("text analytics") OR ("textual data analysis") OR ("text data analysis") OR ("text analysis") OR ("speech and language technology") OR ("language modeling") OR ("computational semantics")))`
   - Results: 2,237

5. **Virology & Generative AI**
   - Query: `(((virology) OR (epidemiology)) AND (("generative artificial intelligence") OR ("generative AI") OR ("generative deep learning") OR ("generative models")))`
   - Results: 75

6. **Virology & Transformer Models**
   - Query: `(((virology) OR (epidemiology)) AND (("transformer models") OR ("self-attention models") OR ("transformer architecture") OR (transformer) OR ("attention-based neural networks") OR ("transformer networks") OR ("sequence-to-sequence models")))`
   - Results: 262

7. **Virology & Large Language Models**
   - Query: `(((virology) OR (epidemiology)) AND (("large language model") OR (llm) OR ("transformer-based model") OR ("pretrained language model") OR ("generative language model") OR ("foundation model") OR ("state-of-the-art language model")))`
   - Results: 183

8. **Virology & Multimodal Models**
   - Query: `(((virology) OR (epidemiology)) AND (("multimodal model") OR ("multimodal neural network") OR ("vision transformer") OR ("diffusion model") OR ("generative diffusion model") OR ("diffusion-based generative model") OR ("continuous diffusion model")))`
   - Results: 121

---

Total records before deduplication: 12,980  
Total records after deduplication based on PMID: 11,450

## 🗂️ Files Included
- `collection_with_abstracts.csv`: The main dataset containing unique papers and their abstracts.
