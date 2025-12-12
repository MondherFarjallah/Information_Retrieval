# Information Retrieval (Python)

In this repository I collect small Information Retrieval exercises I built in Python, focused on:
1) indexing + searching text with Elasticsearch,
2) entity annotation and semantic relatedness,
3) basic text exploration with word clouds.

## Files
- `indexing.py`
  - Connects to an Elasticsearch index
  - Creates mappings/analyzers and indexes documents
  - Runs example queries (match/bool/range) and scoring/boosting exercises

- `annotators.py`
  - Calls online annotators (TAGME + SWAT) via REST APIs to extract entities from text
  - Filters noisy annotations (e.g., by confidence/rho)
  - Computes entity relatedness (TAGME rel endpoint)
  - Optional: compares semantic similarity using Wikipedia2Vec embeddings (cosine similarity)

- `word_clouds.py`
  - Loads a text file and tokenizes it
  - Normalizes text (lowercase, unicode cleanup), removes stopwords
  - (Optional) stemming
  - Builds frequency counts and generates a WordCloud

## Requirements
You can put dependencies in `requirements.txt` like:
- elasticsearch==7.14.0
- requests
- nltk
- wordcloud
- unidecode
- matplotlib
- numpy
- scikit-learn
- wikipedia2vec

## Configuration / Secrets (important)
- If you use Elasticsearch credentials, do **not** commit them.
  - Create `config.json` locally (and add it to `.gitignore`)
  - Commit a safe template like `config.example.json`
- If you use TAGME/SWAT tokens, store them in an environment variable or a local config file that you don’t push.

## Notes
This repo is learning-focused: the scripts are written to practice common IR tasks (indexing, retrieval, scoring, annotation, and text preprocessing).
