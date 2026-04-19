# Enron Email Topic Modelling

## Project overview
This project applies topic modelling to the **Enron Email Dataset** in order to identify the main themes in employee communication.

The main goal is not just to generate topics mechanically, but to build a pipeline that produces **interpretable, defensible, and academically stronger results**.  
Because raw email corpora are noisy, the project focuses heavily on preprocessing, filtering, duplicate removal, and topic validation before interpreting the final themes.

---

## Research question
**What are the main themes in employee communication in the Enron email corpus?**

---

## Objectives
The project aims to:

- clean and standardize raw Enron email text,
- remove noisy documents, template-heavy messages, and duplicated content,
- preserve meaningful business phrases,
- compare several topic-modelling solutions,
- evaluate topic quality using both quantitative and qualitative criteria,
- select the most interpretable final model,
- provide a final thematic interpretation of employee communication.

---

## Dataset
The project uses the **Enron Email Dataset** from Kaggle:

- Dataset: `wcukierski/enron-email-dataset`
- Main file used: `emails.csv`

By default, the notebook loads the dataset via `kagglehub`.  
A local CSV fallback can also be used if needed.

---

## Methodology

### 1. Data loading
The dataset is loaded from KaggleHub or from a local `emails.csv` file.

### 2. Text preprocessing
The notebook performs extensive preprocessing to improve topic quality:

- lowercasing,
- HTML decoding,
- removal of email headers,
- removal of reply chains and forwarded message blocks,
- removal of legal / confidentiality boilerplate,
- removal of newsletter-like and administrative noise,
- whitespace normalization.

### 3. Document quality filtering
Several diagnostics are used to remove weak documents, including:

- document length,
- lexical diversity,
- maximum token concentration,
- noise flags,
- residual family / template indicators.

This step is important because short, repetitive, or template-heavy emails can dominate topics and reduce interpretability.

### 4. Duplicate removal
The project removes:

- **exact duplicates**
- **near-duplicates** based on normalized document signatures

This reduces the risk that repeated templates artificially shape the topic structure.

### 5. Tokenization and phrase detection
The cleaned documents are tokenized and processed with phrase detection to preserve multi-word expressions such as:

- `credit_risk`
- `master_agreement`
- `gas_price`

This improves semantic interpretability compared with treating each word separately.

### 6. Stopword construction
The final stopword list combines:

- standard English stopwords,
- domain-specific email stopwords,
- very frequent weak corpus terms.

This helps suppress generic email vocabulary and emphasize meaningful thematic signals.

### 7. Topic modelling
The notebook uses:

- **LDA (Latent Dirichlet Allocation)** as the main model
- **NMF (Non-negative Matrix Factorization)** as a comparison model

Several candidate topic numbers are tested.

### 8. Model evaluation
Candidate LDA models are compared using:

- **perplexity**
- **coherence**
- **topic diversity**
- **topic balance**
- **stability across random seeds**

The final choice is not based only on one metric.  
It is supported by both numerical evaluation and qualitative review of representative emails.

### 9. Final interpretation
After comparing models, the final solution is manually selected as the most interpretable one.

The final notebook interprets **5 main topics**:

1. Informal and personal employee communication  
2. California energy market and regulatory affairs  
3. Legal, credit, and contract documentation  
4. Trading activity and deal-flow reporting  
5. Internal operations, training, and corporate coordination  

---

## Repository structure
```text
.
├── enron_topic_modelling.ipynb
├── README.md
└── requirements.txt
