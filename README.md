# animal-text-classifier
**Project Overview**
This project focuses on building and evaluating text classification models to distinguish between text snippets related to "dogs" and "cats". It utilizes scikit-learn's TfidfVectorizer for text feature extraction, SMOTE for handling class imbalance, and Multinomial Naive Bayes and Bernoulli Naive Bayes classifiers.
**Data**
The dataset used is Animal_csv.csv, which contains text and a corresponding label (dogs or cats).
- Data Imbalance: The dataset is imbalanced, with approximately 60% "dogs" and 40% "cats" entries.
- Preprocessing: The categorical labels ("dogs" and "cats") are encoded numerically (1 for "dogs", 0 for "cats").
**Methodology**
1.Data Loading and Initial Exploration:
  - The Animal_csv.csv file is loaded into a pandas DataFrame.
  - Initial data exploration confirmed the text and label columns.
  - The class distribution was analyzed, revealing the imbalance.

2.Train-Validation-Test Split:
  - The data is split into training, validation, and test sets with an 80:10:10 ratio, respectively. Stratification is used to maintain the label distribution across splits.
3. Feature Extraction (TF-IDF):
  - TfidfVectorizer is used to convert the text data into numerical feature vectors (Bag-of-Words with TF-IDF weighting).
4.Handling Class Imbalance (SMOTE):
  - SMOTE (Synthetic Minority Over-sampling Technique) is applied within the pipeline to address the class imbalance by oversampling the minority class.
5.Model Training and Evaluation (Naive Bayes):
  Two types of Naive Bayes classifiers are used:
    - MultinomialNB
    - BernoulliNB
  - Each classifier is integrated into a Pipeline with TfidfVectorizer and SMOTE.
  - Models are trained on the training set and evaluated on the training, validation, and test sets using F1-score and Accuracy.

**Conclusion**
- The Multinomial Naive Bayes model generally shows higher F1-scores and accuracy across all sets (train, validation, and test) compared to the Bernoulli Naive Bayes model.
- However, the Multinomial model exhibits a larger difference between its training scores and validation/test scores, indicating a tendency to overfit the training data more than the       Bernoulli model.
- Despite the overfitting tendency, the Multinomial model still performs better on the test set.


