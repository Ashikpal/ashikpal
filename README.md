## Hi there 👋

<!--
**Ashikpal/ashikpal** is a ✨ _special_ ✨ repository because its `README.md` (this file) appears on your GitHub profile.

Here are some ideas to get you started:

- 🔭 I’m currently working on ...
- 🌱 I’m currently learning ...
- 👯 I’m looking to collaborate on ...
- 🤔 I’m looking for help with ...
- 💬 Ask me about ...
- 📫 How to reach me: ...
- 😄 Pronouns: ...
- ⚡ Fun fact: ...
-->
Data Loading and Preprocessing: You successfully loaded the email dataset, handled missing values, and performed basic text cleaning like lowercasing.
Exploratory Data Analysis (EDA): You visualized the class distribution and analyzed the distribution of special characters in legitimate versus phishing emails. You also identified and visualized the most common words in phishing emails.
Model Exploration (RoBERTa): You successfully integrated RoBERTa, a powerful transformer model, into your workflow for text classification. You loaded its tokenizer and model, prepared the dataset for training, and set up the training arguments and trainer. The RoBERTa model was trained to classify emails.
Feature Engineering: You developed custom feature extraction methods, including:
Stylometry Features: Captured writing style nuances like average word length, average sentence length, uppercase ratio, punctuation count, and digit count.
Perplexity Score: Used a GPT-2 model to calculate email perplexity as a potential indicator of AI-generated content.
Simulated Metadata Features: Implemented analysis of simulated WHOIS, SPF/DKIM, and URL entropy based on text patterns.
Ensemble Model Development: You built an ensemble model combining the RoBERTa model with an XGBoost classifier. The XGBoost model utilized the extracted stylometry, perplexity, and simulated metadata features.
Ensemble Training: You trained the XGBoost model on the traditional features and then trained a Logistic Regression meta-classifier on the combined probability predictions from the RoBERTa and XGBoost models on the validation set.
Data Augmentation: You successfully augmented the training dataset with 2,000 simulated phishing emails (real templates, AI-generated, and adversarial) to address class imbalance and potentially improve model robustness.
Ensemble Evaluation: You evaluated the final ensemble model on the test set, achieving high performance metrics:
Accuracy: 0.9973
Precision: 0.9984
Recall: 0.9968
F1 Score: 0.9976 The confusion matrix also showed excellent performance with very few misclassifications.
Model Saving: You saved all the components of your ensemble model (RoBERTa model and tokenizer, XGBoost model, meta-classifier, and feature preprocessor) to Google Drive for later use in inference.
Streamlit App: You created a Streamlit application to provide a user interface for predicting whether an email is phishing using your trained ensemble model. You also set up pyngrok to create a public URL for your Streamlit app.
