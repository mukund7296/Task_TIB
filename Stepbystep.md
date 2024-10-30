To start this project step-by-step, here’s a detailed breakdown:

### Step 1: Set Up the Environment

1. **Install Required Software**:
   - Ensure **Python 3.8+** is installed.
   - Set up a virtual environment to keep dependencies organized:
     ```bash
     python3 -m venv env
     source env/bin/activate  # On Windows use `env\Scripts\activate`
     ```

2. **Install Required Libraries**:
   - Install the dependencies listed in the `requirements.txt` file:
     ```bash
     pip install -r requirements.txt
     ```

### Step 2: Define PubMed Queries

1. **Construct PubMed Queries**:
   - Use the queries provided to search on PubMed for relevant records. Each query targets a specific deep learning technology in virology or epidemiology. You can issue these queries through the [PubMed Advanced Search](https://pubmed.ncbi.nlm.nih.gov/advanced/) or via the PubMed API if you prefer automation.

2. **Run Each Query Individually**:
   - Copy each query and run it separately on PubMed, filtering for articles with abstracts where possible. Example query:
     ```
     (((virology) OR (epidemiology)) AND (("deep learning") OR ("deep neural networks")))
     ```
   - **Export results** to a CSV for each query, saving them with appropriate filenames (e.g., `virology-deep-learning.csv`).

### Step 3: Compile and Deduplicate Results

1. **Load CSV Files**:
   - Load each CSV file with metadata and abstracts using Python:
     ```python
     import pandas as pd
     
     df1 = pd.read_csv('virology-neural-networks.csv')
     df2 = pd.read_csv('virology-deep-learning.csv')
     # Continue loading other CSVs as needed
     ```

2. **Merge Data**:
   - Concatenate data from all CSVs:
     ```python
     all_data = pd.concat([df1, df2, ...])  # Add all dataframes here
     ```

3. **Remove Duplicates**:
   - Use the PMID column to remove duplicate records:
     ```python
     all_data = all_data.drop_duplicates(subset=['PMID'])
     ```

4. **Save the Consolidated Data**:
   - Save the deduplicated dataset as `collection_with_abstracts.csv`:
     ```python
     all_data.to_csv('collection_with_abstracts.csv', index=False)
     ```

### Step 4: Analyze the Dataset

1. **Explore the Dataset**:
   - Open `collection_with_abstracts.csv` to ensure data integrity and familiarize yourself with its contents.
   - Check the structure and data fields to prepare for semantic filtering and classification in the next steps.

### Step 5: Implement Filtering and Classification

1. **Filter Papers Based on Semantic Relevance**:
   - Use a pre-trained NLP model (e.g., SciBERT or BioBERT) to identify papers that specifically use deep learning in virology/epidemiology.
   - You can perform semantic filtering based on keywords like “neural network” or “deep learning” in the title or abstract fields.

2. **Classify Each Relevant Paper**:
   - For relevant papers, classify them based on method:
     - `text mining`, `computer vision`, `both`, or `other`.
   - Store this classification as a new column in the dataset.

3. **Extract Deep Learning Methods**:
   - Use a Named Entity Recognition (NER) model to extract the method names from the abstracts and store these in a new column.

### Step 6: Save and Document Your Results

1. **Save the Final Processed Dataset**:
   - Save the final dataset with filtered, classified, and extracted method information:
     ```python
     all_data.to_csv('final_processed_data.csv', index=False)
     ```

2. **Update Documentation**:
   - Update your `README.md` file with clear instructions and details about the final processed data. Include any observations or notable insights from the dataset.

3. **Publish or Share the Repository**:
   - If you're using Git, commit your changes and push them to a repository (GitHub, GitLab, etc.) for easy access and sharing.

Following these steps sequentially will help you create, organize, and process your dataset efficiently. 
