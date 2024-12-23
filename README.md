# Forum Analysis and Enhancement

In collaboration with Marina Gómez, María Magro y Ángela Durán.

## Introduction

This project focuses on analyzing user-generated content from an online forum to extract meaningful insights and improve organization. Techniques such as topic modeling, sentiment analysis, and clustering are applied to explore the variability in language, sentiment, and themes across forum posts. Additionally, recommendations for enhancing user experience are developed based on the findings.

---

## Datasets

### Primary Datasets
- **Forum Dataset**: Scraped from [Something Awful Forums](https://forums.somethingawful.com).
- **Emoji Dataset**: Sourced from [Kaggle](https://www.kaggle.com/datasets/subinium/emojiimage-dataset).

### Supplementary Datasets
- **NRC Lexicon Dataset & Vader Lexicon** for sentiment analysis.
- **GloVe Pre-trained Embeddings** for word vectorization.

---

## Data Collection

Web scraping was performed using Python's `BeautifulSoup` library, with over 25,000 forum posts collected.

---

## Preprocessing Pipeline

Steps included:
1. HTML tag removal.
2. Contraction expansion.
3. Tokenization.
4. Lemmatization.
5. Stopword removal.

---

## Vectorization Techniques

1. **TF-IDF**
2. **GloVe**
3. **LDA (Mallet)**

Dimensionality reduction was achieved using:
- **SVD**: Applied to TF-IDF.
- **PCA**: Applied to GloVe embeddings.

---

## Clustering

### Optimal Number of Clusters
- For **GloVe**, 95 clusters gave the highest combined score, but the complexity was impractical.
- We chose **65 clusters** (second-highest score, silhouette: 0.9658), balancing performance and interpretability.

### Final Choice
- **TF-IDF with 15 clusters** was selected as it aligned with its elbow method and provided a manageable level of detail for further analysis.

---

## Sentiment Analysis and Emoji Recommendation

### Methodology

#### Sentiment Analysis
- **NRC Lexicon**: Classified posts and emojis into emotions (e.g., 'Joy', 'Anger').
- **Vader**: Polarity scores for positive, negative, or neutral sentiment.

#### Emoji Recommendation
1. **Cosine Similarity**: Matched forum posts to emojis with the closest emotional tone.
2. **Top 3 Emojis**: Recommended for each post.

#### Topic Modeling for Emoji Recommendation
1. **GloVe Embeddings**: Represented topics and emojis.
2. **Cosine Similarity**: Mapped topics to emojis, ensuring rich and diverse interpretations.

---

## Dashboard

### Features

1. **Cluster Visualization**
   - Interactive scatter plots of clusters.
   - Post details on selection (e.g., title, cluster, recommended emojis).

2. **Post Selector**
   - Filter posts by sentiment, topic, and emotion.

3. **Emoji Cloud**
   - Highlights emotionally relevant emojis for user exploration.

4. **Emoji Recommendation Pipeline**
   - Processes new posts with sentiment analysis and clustering.

---
