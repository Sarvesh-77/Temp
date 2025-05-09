# Temp
import pandas as pd
from sklearn.feature_extraction.text import TfidfVectorizer
from sklearn.decomposition import NMF

# Assuming you have a DataFrame with your texts and their cluster labels
# Example:
# df = pd.DataFrame({'text': [...], 'cluster': [...]})

n_topics_per_cluster = 3  # you can change this
top_n_words = 5

def topic_words(tfidf, nmf_model, feature_names, top_n=5):
    topics = []
    for topic_weights in nmf_model.components_:
        top_words = [feature_names[i] for i in topic_weights.argsort()[:-top_n-1:-1]]
        topics.append(top_words)
    return topics

# Loop through all 20 clusters
for cluster_id in range(20):
    print(f"\n=== Cluster {cluster_id} ===")

    # Filter texts in this cluster
    cluster_texts = df[df['cluster'] == cluster_id]['text'].tolist()
    if not cluster_texts:
        print("No data in this cluster.")
        continue

    # TF-IDF vectorization
    vectorizer = TfidfVectorizer(stop_words='english', max_features=1000)
    tfidf_matrix = vectorizer.fit_transform(cluster_texts)
    feature_names = vectorizer.get_feature_names_out()

    # NMF topic modeling
    nmf_model = NMF(n_components=n_topics_per_cluster, random_state=0)
    nmf_model.fit(tfidf_matrix)

    # Extract top words per topic
    topics = topic_words(tfidf_matrix, nmf_model, feature_names, top_n=top_n_words)

    # Display as table
    topic_df = pd.DataFrame(topics, columns=[f"Word {i+1}" for i in range(top_n_words)])
    topic_df.index = [f"Topic {i+1}" for i in range(n_topics_per_cluster)]
    print(topic_df.to_string())
