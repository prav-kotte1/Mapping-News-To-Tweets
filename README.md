# Mapping-News-To-Tweets
### **Course: Information Retrieval and Extraction (IRE)**

This project explores the relationship between formal news media and social media discourse. By identifying the most significant terms in news articles, we attempted to retrieve the most relevant conversations happening on Twitter.

---

## Contributors
* **Pravallika** (2022IMT-062) — [@prav-kotte1](https://github.com/prav-kotte1)
* **Shreya** (2022IMT-053) — [@shreyajagrotu25](https://github.com/shreyajagrotu25)
* **Harsha** (2022IMT-029) — [@b-harsha-v](https://github.com/b-harsha-v)

---

## Methodology

The project utilizes a keyword-based retrieval pipeline to link structured news data to unstructured tweet data.

### 1. Keyword Extraction
We utilized **TF-IDF (Term Frequency-Inverse Document Frequency)** to analyze each news article. For every article, we extracted the **top 10 words** with the highest TF-IDF scores, ensuring we captured the most unique and descriptive identifiers for the story.

### 2. Mapping & Similarity Metrics
We implemented three different mathematical approaches to map these 10 keywords to the tweet dataset:

| Technique | Description |
| :--- | :--- |
| **Weighted Term Presence** | Calculates a score based on the presence of keywords in a tweet, weighted by their specific TF-IDF importance. |
| **Cosine Similarity** | Measures the cosine of the angle between the vector representations of the news keywords and the tweet text. |
| **Jaccard Similarity** | Evaluates the overlap between the set of news keywords and the set of words in a tweet (Intersection over Union). |

---

## Results & Observations

The performance of the mapping varied depending on the nature of the content:

* **Optimal:** High precision for articles containing unique proper nouns (e.g., specific names, locations, or technical terms).
* **Average:** Required additional tuning for general topics where common vocabulary overlapped across unrelated tweets.
* **Poor:** Struggles were noted in cases where tweets used heavy slang, abbreviations, or lacked context that matched the formal tone of the news articles.

---

## Future Scope
* Integrating **Word Embeddings (Word2Vec/GloVe)** or **Transformers (BERT)** to capture semantic similarity rather than just keyword matching.
* Incorporating **Temporal Filtering** to match news and tweets within the same time window.
* Advanced tweet cleaning to handle hashtags, emojis, and social media shorthand.
