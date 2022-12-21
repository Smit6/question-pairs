# question-pairs

### Objective
A Natural Language Processing system to classify whether question pairs are duplicated. 


### Dataset: [Quora Question Pairs](https://www.kaggle.com/competitions/quora-question-pairs/data)

Quora used a Random Forest model to identify duplicate questions, and has provided this dataset through a Kaggle competition to explore advanced techniques to find high quality answer resulting an improved experience for Quora writers, seekers, and readers.


### Steps taken for building an optimal NLP system
1. Exploratory data analysis (EDA) - exploration.ipynb
2. Bag of Words (BOW) & Ensemble (RF & XGBoost) - bag_of_words.ipynb
3. Advanced Features - custom_features_dataset.ipynb
4. Ensemble on Advanced Features - custom_ensemble.ipynb

#### 1. Exploratory data analysis (EDA)
- Gather
- Asses
- Clean
- Explore

#### 2. Bag of Words (BOW) & Ensemble (RF & XGBoost)
- Generate BOW for the explored dataset
- Implement following ensemble techniques on Bag Of Words features
  - Random Forest
  - XGBoost

#### 3. Advanced Features
- Extract Advanced Features from questions
- Following features has been extracted
  - Bag Of Words
  - Custom Features
    - q1len
    - q2len
    - q1words
    - q2words
    - wordscommon
    - wordstotal
    - wordsshare
  - Token Features
    - cwc_min - num of common words / min(words(q1), words(q2))
    - cwc_max - num of common words / max(words(q1), words(q2))
    - csc_min - num of stop words / min(stopwords(q1), stopwords(q2))
    - csc_max - num of stop words / max(stopwords(q1), stopwords(q2))
    - ctc_min - num of common tokens / min(tokens(q1), tokens(q2))
    - ctc_max - num of common tokens / max(tokens(q1), tokens(q2))
    - last_word_equal
    - first_word_equal
  - Length Based Features
    - mean_len
    - abs_len_diff
    - longest_substr_ratio
  - Fuzzy Features
    - fuzz_ratio
    - fuzz_partial_ratio
    - token_sort_ratio
    - token_set_ratio

4. Ensemble on Advanced Features
- Implement following ensemble techniques on Advanced features
  - Random Forest
  - XGBoost

### Conclusion
Inclusion of advanced features to the BOW features improved the performance of both Random Forest and XGBoost. We are getting ~83% accuracy for the Random Forest model, which is impressive.