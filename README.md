# -Product-Similarity-Analysis-and-Recommendation-System-Using-Text-Mining-
Content-based Amazon product recommendation system using TF-IDF and cosine similarity for suggesting similar items based on titles and details.

Data Processing
Combined JSONL files from multiple categories into a single DataFrame.
Extracted and parsed product details (e.g., brand, material) into structured text.
Cleaned text by removing punctuation, converting to lowercase, and trimming spaces.
Feature Engineering
Applied TF-IDF vectorization with:
N-grams (unigrams + bigrams)
Stop-word removal
Max features = 10,000 to focus on the most relevant terms.
Similarity Calculation
Computed cosine similarity between product descriptions.
Generated a 14,000 x 14,000 similarity matrix for recommendations.
Recommendation Function
For a given product, the system retrieves the top-N most similar items based on cosine similarity scores.
Evaluation & Insights

Recommendation Quality:
Worked well for beauty and personal care products (e.g., reusable makeup pads with similar materials/brands).
Struggled with Digital_Music due to less distinctive textual features.
Similarity Distribution:
Most products had low similarity scores (0.1–0.3), but some pairs scored >0.5, indicating strong matches.
Visualizations:
Heatmaps and histograms showed clustering patterns and score distributions.
Limitations & Improvements

Data Quality: Some categories (e.g., Digital_Music) had sparse or generic descriptions, reducing recommendation accuracy.
Enhancements:
Incorporate user behavior data (e.g., ratings, purchases) for hybrid recommendations.
Use word embeddings (Word2Vec, BERT) for deeper semantic analysis.
Address cold-start problems with popularity-based fallbacks.
Technologies Used

Python Libraries: Pandas, Scikit-learn (TF-IDF, cosine similarity), Matplotlib/Seaborn.
Methods: Text preprocessing, TF-IDF, cosine similarity, heatmap visualization.

