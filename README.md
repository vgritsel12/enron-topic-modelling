# Enron Email Topic Modelling

This project explores the Enron Email Dataset and applies topic modelling methods to identify the main themes of internal corporate communication.

The notebook focuses on working with noisy real-world email data and includes text cleaning, preprocessing, vectorization, topic modelling, model comparison, and interpretation of representative emails.

## Project Objective

The main goal of this project is to discover the dominant topics discussed in the Enron email corpus.

This project aims to show how NLP methods can be used on real corporate email data, where the text is often messy, duplicated, technical, and difficult to interpret without careful preprocessing.

## Dataset

The project uses the **Enron Email Dataset**, a well-known dataset of real corporate emails made public during the investigation of Enron’s collapse.

The dataset contains email text with many typical problems of real-world text data, such as:

- email headers
- forwarded content
- signatures
- disclaimers
- duplicated messages
- very short administrative emails
- technical noise

Because of this, the dataset is a strong example for practical NLP analysis and topic modelling.

## Methods

The project includes the following main stages:

1. **Data loading**
2. **Text cleaning and preprocessing**
3. **Corpus filtering**
4. **Text vectorization**
5. **Topic modelling**
6. **Model comparison**
7. **Topic interpretation**

### Preprocessing steps

The preprocessing pipeline includes:

- removing email headers and technical metadata
- cleaning the main email body
- normalizing text
- removing noisy fragments
- filtering very short or low-information emails
- removing duplicate messages
- handling stopwords more carefully

### Modelling methods

The notebook uses:

- **LDA (Latent Dirichlet Allocation)**
- **NMF (Non-negative Matrix Factorization)**

These models are compared in order to choose the most interpretable result.

## Tools and Libraries

This project uses:

- Python
- pandas
- NumPy
- scikit-learn
- gensim
- regular expressions (regex)
- Jupyter Notebook

## Results

The analysis shows that topic modelling on email data depends strongly on preprocessing quality.

The improved workflow makes the topics more interpretable by reducing technical noise and focusing more clearly on meaningful content.

The project also demonstrates that model outputs should not be interpreted only through top words. Representative emails are also important for understanding what each topic really means.

## Repository Contents

- `enron_topic_modelling.ipynb` — main notebook with the full analysis
- `README.md` — project description
- `requirements.txt` — required Python packages

## How to Run

1. Clone or download this repository
2. Install the required libraries
3. Open the notebook in Jupyter
4. Run all cells step by step

Example installation:

```bash
pip install -r requirements.txt
