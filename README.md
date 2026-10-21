# Nike earnings-call NLP (Elliott Hill era)

Text analytics on NIKE, Inc.'s official earnings-call transcripts since Elliott Hill became CEO on Oct 14, 2024
(Q2 FY25 through Q1 FY27): **semantic research** and **frequency significance detection**.

[![Open In Colab](https://colab.research.google.com/assets/colab-badge.svg)](https://colab.research.google.com/github/duytranm/nike-earnings-nlp/blob/main/notebooks/nike_earnings_nlp.ipynb)

## What's inside
| Path | Purpose |
|---|---|
| `notebooks/nike_earnings_nlp.ipynb` | Main analysis notebook (runs on Google Colab) |
| `nlp/parse.py` | PDF -> paragraphs tagged by call, speaker, role (CEO/CFO/Analyst) and section (prepared remarks / Q&A) |
| `nlp/text.py` | Tokenization, adjacent-word phrases, plural folding, key-word-in-context |
| `nlp/stats.py` | Dunning log-likelihood keyness + Log Ratio + Benjamini-Hochberg FDR; quasi-Poisson trend tests |
| `nlp/themes.py` | Editable theme dictionaries with call-over-call rate tests |
| `nlp/sentiment.py` | Loughran-McDonald finance-lexicon tone, with negation handling |
| `nlp/semantic.py` | Hybrid semantic search (BM25 + LSA + optional dense embeddings) and NMF topic discovery |
| `data/corpus.csv` | Parsed corpus: 923 paragraphs from 8 calls |
| `scripts/build_corpus.py` | Re-download and re-parse the transcripts (`--download`) |

## Run locally
```bash
pip install -r requirements.txt
jupyter lab notebooks/nike_earnings_nlp.ipynb
```

## Sources and terms
* Transcripts: NIKE, Inc. official earnings-call transcripts, investors.nike.com, provided by Nike "for reference purposes".
* Sentiment lexicon: Loughran-McDonald Master Dictionary (Loughran & McDonald, 2011), sraf.nd.edu, for non-commercial research use.
* This repository is independent research and not affiliated with NIKE, Inc. Nothing here is investment advice.
