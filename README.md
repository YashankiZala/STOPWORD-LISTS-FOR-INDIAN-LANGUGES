# Transformer-Based Stopword Lists for Indian Languages

This repository contains **stopword lists** generated from nine pre‑trained transformer and LLM models for five Indian languages. The stopwords are extracted using a novel embedding‑based method and are intended to improve information retrieval (IR) performance in low‑resource Indian languages.

## Languages Covered

| Language | Folder Name |
|----------|--------------|
| Gujarati | `gujarati/` |
| Hindi    | `hindi/`    |
| English  | `english/`  |
| Marathi  | `marathi/`  |
| Bengali  | `bengali/`  |

## Models Used

Stopword lists are generated from **nine** different transformer/LLM architectures, grouped into three families:

### Encoder‑Only Models (5)
- **MuRIL** – Multilingual Representations for Indian Languages [1]
- **mBERT** – Multilingual BERT
- **XLM‑R** – Cross‑lingual Language Model – RoBERTa [2]
- **E5** – EmbEddings from bidirEctional Encoder rEpresentations [3]
- **Instructor** – Instruction‑fine-tuned text embeddings [4]

### Encoder‑Decoder Models (2)
- **mT5** – Multilingual T5 [5]
- **mBART** – Multilingual BART [6]

### Decoder‑Only Models (2)
- **BLOOM** – BigScience Large Open‑science Open‑access Multilingual Language Model [7]
- **Mistral** – Mistral 7B [8]

## Repository Structure

├── gujarati/
│ ├── muril_stopwords.txt
│ ├── mbert_stopwords.txt
│ ├── xlmr_stopwords.txt
│ ├── e5_stopwords.txt
│ ├── instructor_stopwords.txt
│ ├── mt5_stopwords.txt
│ ├── mbart_stopwords.txt
│ ├── bloom_stopwords.txt
│ └── mistral_stopwords.txt
├── hindi/
│ └── (same nine files)
├── english/
│ └── (same nine files)
├── marathi/
│ └── (same nine files)
├── bengali/
│ └── (same nine files)
└── README.md


Each `.txt` file contains one stopword per line. The stopwords are lowercased and stripped of punctuation.

## Performance Gains (MAP Improvement over Baseline)

Using these stopword lists in combination with standard retrieval models (BM25, TF‑IDF, etc.) yields significant improvements:

| Language | Best Model | Max MAP Gain |
|----------|------------|--------------|
| Gujarati | E5         | +9.9%        |
| Hindi    | mT5        | +95.07%      |
| English  | mT5        | +0.71%       |
| Marathi  | XLM‑R      | +5.02%       |
| Bengali  | MuRIL      | +2.41%       |

Detailed experimental results are available in our paper.
   
