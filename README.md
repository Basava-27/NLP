📝 NLP Fundamentals – Text Preprocessing & Vectorization

This repository covers text preprocessing techniques and vectorization methods used in Natural Language Processing (NLP). It explains the journey from raw text to numerical vectors that can be used in machine learning models.

📍 Step 1: Text Preprocessing
1. Tokenization

Splitting text into smaller units (tokens), usually words or subwords.

2. Stop Words Removal

Eliminating common words (e.g., the, is, and) that do not contribute much meaning.

3. Stemming

Reducing words to their root form by chopping off suffixes.
Example use cases: Spam classification, review classification.

4. Lemmatization

Reducing words to their base or dictionary form using vocabulary and morphological analysis.
Example use cases: Text summarization, language translation, chatbots.

📍 Step 2: Words → Vectors

Once text is cleaned and preprocessed, we need to convert it into numerical representations.

1. One-Hot Encoding

Each word is represented as a binary vector.

Advantages: Simple to implement.

Disadvantages: Sparse matrix, Out-of-Vocabulary (OOV) issues, no semantic meaning captured, variable size.

Example:

Sentences:
A man eat food
Cat eat food
People watch Krish yt

Vocabulary:
A, man, eat, food, cat, people, watch, krish, yt


One-hot representation:

A:      [1 0 0 0 0 0 0 0 0]
man:    [0 1 0 0 0 0 0 0 0]
...

2. Bag of Words (BoW)

Represents text by word frequency counts.

Ignores grammar and order of words.

Can be binary (0/1) or frequency-based.

Example:

D1: he is a good boy  → good boy
D2: she is a good girl → good girl
D3: boys and girls are good → boy girl good


Vocabulary frequency:

good: 3
boy: 2
girl: 2


Advantages: Simple and intuitive.
Disadvantages: Sparsity, OOV issues, loses word order, no semantic meaning.

3. TF-IDF (Term Frequency – Inverse Document Frequency)

Adjusts word frequency based on how often it appears across documents.

Reduces the weight of common words and increases the weight of rare but important words.

4. Word2Vec

Uses neural networks to create dense vector representations of words.

Captures semantic meaning and relationships between words.

📍 Improving Semantic Capture – N-Grams

Combines sequences of words to retain some context.
Example bigrams: (good boy), (good girl)

Sentence	good	boy	girl	(good boy)	(good girl)
Sent 1	1	1	0	1	0
Sent 2	1	0	1	0	1
Sent 3	1	1	1	0	0


📍 Cosine Similarity

Measures similarity between two vectors based on the cosine of the angle between them.

Formula:
Cosine Similarity=1−cos(θ)


📂 Data Flow in NLP
DATASET
   ↓
Text Preprocessing (Tokenization, Stop Words, Stemming/Lemmatization)
   ↓
Feature Extraction (One-Hot, BoW, TF-IDF, Word2Vec, N-Grams)
   ↓
Vectors ready for ML models
