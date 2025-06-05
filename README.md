**Simple Movie Recommendation System**

Using the TMDB 5000 dataset, this project implements a content-based recommender in Python:

1. **Data Preprocessing**

   * Load and merge “movies” and “credits” CSVs on `movie_id`
   * Parse JSON fields (`genres`, `keywords`, `cast`, `crew`) into lists
   * Extract top-3 cast members and director; clean overview text
   * Combine (`genres_list + keywords_list + cast_list + [director] + overview_list`) into a single `merged_details` string per movie

2. **Vectorization & Similarity**

   * Convert `merged_details` into a document-term matrix using `CountVectorizer` (or `TfidfVectorizer`)
   * Compute pairwise cosine similarity between all movie vectors

3. **Recommendation Function**

   * Map each title to its DataFrame index
   * Given a title, find its similarity scores, sort descending, and return the top N most similar movies
