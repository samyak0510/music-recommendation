# Song Recommendation System (Lyrics + Metadata + Optional Spotify Audio Features)

This project implements a **music recommender** that combines:

- **Sentence-BERT embeddings** for semantic lyric similarity  
- **TF-IDF vectors** for metadata similarity (genres, artists, lyrics)  
- **(Optional)** Spotify audio features for re-ranking results  

---

## Features

- Search with **natural-language queries** (e.g. "moody indie for a rainy night")  
- Recommend songs from a **seed track** (title and year)  
- Hybrid scoring: semantic lyrics + keyword metadata  
- Optional re-ranking via Spotify audio features (tempo, energy, valence, ..)

---

## Installation

```bash
# clone
git clone https://github.com/your-username/song-recommender.git
cd song-recommender

```

**requirements.txt**

```
pandas
numpy
scikit-learn
sentence-transformers
spotipy
```

---

## Dataset

Download **Genius Song Lyrics with Language Information** from [https://www.kaggle.com/datasets/carlosgdcj/genius-song-lyrics-with-language-information] 
and place it in the project root as:

```
song_lyrics.csv
```

---

## Spotify API Setup (Optional)

1. Create a Spotify Developer app: <https://developer.spotify.com/>  
2. Note your **Client ID**, **Client Secret**, and set a **Redirect URI**  


## Code Overview

| Step | File / Function | Purpose |
|------|-----------------|---------|
| 1 | Data loading & preprocessing | Filters English songs, builds `doc_text` |
| 2 | Embeddings | `SentenceTransformer("all-MiniLM-L6-v2")` for lyrics |
| 3 | Indexing | `NearestNeighbors` on lyric-embeddings & TF-IDF |
| 4 | Recommendation | `recommendByText`, `recommendBySeed`, `hybridScore` |
---

## License

Apache License 2.0
