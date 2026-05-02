# Transformer-Based Stopword Lists for Indian Languages

This repository contains **stopword lists** generated from nine pre‑trained transformer and LLM models for five Indian languages. The stopwords are extracted using a novel embedding‑based method and are intended to improve information retrieval (IR) performance in low‑resource Indian languages.

## Languages Covered

| Language | Folder Name |
|----------|--------------|
| Gujarati | `Gujarati/` |
| Hindi    | `Hindi/`    |
| English  | `English/`  |
| Marathi  | `Marathi/`  |
| Bengali  | `Bengali/`  |

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

text

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

Detailed experimental results are available in our paper [9].

## How to Use

1. **Clone the repository**
   ```bash
   git clone https://github.com/yourusername/stopwords-indian-languages.git
   cd stopwords-indian-languages
Load a stopword list (Python)

python
language = "hindi"
model = "mt5"
with open(f"{language}/{model}_stopwords.txt", "r", encoding="utf-8") as f:
    stopwords = set([line.strip() for line in f])
Apply in your IR pipeline – remove tokens that appear in the stopword set before indexing or querying.

License
This repository is released under the MIT License. The stopword lists are free for academic and commercial use.

References
[1] Khanuja et al. (2021). MuRIL: Multilingual Representations for Indian Languages. EACL.

[2] Conneau et al. (2020). Unsupervised Cross-lingual Representation Learning at Scale. ACL.

[3] Wang et al. (2024). Text Embeddings by Weakly-Supervised Contrastive Pre-training. ACL.

[4] Su et al. (2023). One Embedder, Any Task: Instruction-Finetuned Text Embeddings. ACL Findings.

[5] Xue et al. (2021). mT5: A massively multilingual pre-trained text-to-text transformer. NAACL.

[6] Liu et al. (2020). Multilingual Denoising Pre-training for Neural Machine Translation. TACL.

[7] Scao et al. (2023). BLOOM: A 176B-Parameter Open-Access Multilingual Language Model. JMLR.

[8] Jiang et al. (2023). Mistral 7B. arXiv preprint.

[9] Sahu and Pal (2023). Effect of stopwords in Indian language IR. Sādhanā.
