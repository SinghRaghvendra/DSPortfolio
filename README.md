**SMS Spam Detection using TensorFlow in Python**
Project Overview

SMS spam detection is the process of automatically classifying incoming text messages as either legitimate (ham) or spam using machine learning and deep learning techniques. This project presents an end-to-end Natural Language Processing (NLP) pipeline using TensorFlow to build and compare multiple deep learning models for spam classification.

The system is designed to identify and filter unwanted, fraudulent, or malicious messages before they reach users, improving both user experience and security.

Objectives
Load and preprocess an SMS spam dataset
Perform feature analysis and compute text statistics
Build a scalable text vectorization pipeline
Implement multiple deep learning models
Evaluate models using robust classification metrics
Visualize and compare model performance

Tech Stack
Python
TensorFlow / Keras
TensorFlow Hub (Universal Sentence Encoder)
Pandas, NumPy
Scikit-learn
Matplotlib, Seaborn

Dataset
SMS Spam Collection Dataset
Format: CSV

Target Variable:
Ham (0)
Spam (1)

Project Pipeline
1. Data Loading
Dataset loaded using Pandas
Encoding handled using latin-1
2. Data Cleaning and Label Encoding
Removed irrelevant columns
Renamed columns for clarity
Converted labels:
Ham → 0
Spam → 1
3. Train-Test Split
80% training data
20% testing data
Converted to NumPy arrays for TensorFlow compatibility
4. Text Statistics
Calculated average words per message
Estimated vocabulary size

These values are critical for configuring sequence length and embedding layers.

5. Text Vectorization

A TextVectorization layer is used to:

Normalize text (lowercasing, punctuation removal)
Convert words into integer sequences
Standardize sequence length

This ensures consistent input for deep learning models.

6. Training and Evaluation Pipeline

Two reusable helper functions were created:

compile_and_fit() → compiles and trains models
get_metrics() → evaluates performance

Evaluation metrics include:

Accuracy
Precision
Recall
F1-score

F1-score is especially important in spam detection as it balances false positives and false negatives.

Models Implemented
Model 1: Dense Embedding Model

Architecture:
Text → Vectorization → Embedding → GlobalAveragePooling → Dense → Output

Key Features:

Fast and efficient
Baseline model
Limited contextual understanding
Model 2: Bidirectional LSTM Model

Architecture:
Text → Vectorization → Embedding → BiLSTM → Dense → Output

Key Features:

Captures sequence dependencies
Reads text in both forward and backward directions
Improves contextual understanding and accuracy

Bidirectional LSTM enhances context by considering both preceding and succeeding words in a sequence.

Model 3: Transfer Learning using Universal Sentence Encoder (USE)

Architecture:
Text → USE → Dense → Output

Key Features:

Uses pretrained sentence embeddings
Captures semantic meaning of entire sentences
Performs best among all models

USE converts sentences into high-dimensional vectors that encode semantic meaning, enabling better classification performance.

Results Summary
Transfer Learning (USE) achieved the best performance
BiLSTM outperformed Dense Embedding due to sequence awareness
Dense model served as an efficient baseline

USE model showed superior recall and F1-score, indicating better detection of spam patterns.

Visualization
Bar Chart
Compares all evaluation metrics across models
Line Graph
Shows performance trends for each model
Key Insights
Data preprocessing is critical for NLP performance
Sequence models improve contextual understanding
Transfer learning significantly boosts accuracy
F1-score is the most reliable metric for spam detection
Future Improvements
Implement Transformer-based models such as BERT
Deploy using FastAPI or Flask
Build a real-time spam filtering system
Integrate with messaging platforms
Project Link

GitHub Notebook:
https://github.com/SinghRaghvendra/DSPortfolio/blob/main/SMS_Spam_Detection_using_TensorFlow_in_Python.ipynb




**SMS Spam Detection using TensorFlow: A Comparative Study of Deep Learning Approaches**
LinkedIn: https://www.linkedin.com/in/raghvendra0027
GitHub: https://github.com/SinghRaghvendra

Introduction

SMS spam remains a significant issue in modern communication systems, often used for phishing, fraud, and unsolicited advertising. Detecting such messages automatically is essential for maintaining user trust and security.

This project explores how deep learning models can be applied to solve this problem, comparing three different approaches with increasing levels of complexity.

Why Spam Detection is Challenging

Spam detection is not just a classification task—it is fundamentally a language understanding problem.

Challenges include:

Short and unstructured text
Ambiguous context
Imbalanced datasets
Evolving spam patterns
Data Preparation

The dataset was cleaned and structured by:

Removing irrelevant columns
Renaming fields
Encoding labels into numeric form

The dataset was then split into training and testing sets to ensure unbiased evaluation.

Text Processing Pipeline

A text vectorization pipeline was implemented to:

Convert text into numerical format
Normalize and clean input
Maintain consistent sequence length

Additionally, dataset statistics such as average message length and vocabulary size were computed to optimize model configuration.

Model 1: Dense Embedding Model

This model acts as the baseline.

Key Idea:

Convert words into embeddings and average them for classification.

Observations:
Fast and simple
Limited understanding of word order
Suitable for benchmarking
Model 2: Bidirectional LSTM

This model improves performance by understanding sequences.

Key Idea:

Process text in both forward and backward directions to capture context.

Observations:
Better contextual understanding
Improved recall and F1-score
Higher computational cost
Model 3: Transfer Learning with Universal Sentence Encoder

This model leverages pretrained knowledge.

Key Idea:

Use a pretrained encoder to convert sentences into meaningful embeddings.

Observations:
Highest performance
Strong semantic understanding
Minimal feature engineering required

Transfer learning models outperform traditional approaches by leveraging large-scale pretrained knowledge.

Model Evaluation

Models were evaluated using:

Accuracy
Precision
Recall
F1-score

Accuracy alone is not sufficient for imbalanced datasets, making F1-score a more reliable metric.

Results and Insights

The comparison reveals a clear progression:

Dense Model → Baseline performance
BiLSTM → Improved contextual learning
USE → Best performance due to semantic understanding

This demonstrates that deeper language understanding leads to better classification.

Industry Perspective

Modern spam detection systems are evolving toward transformer-based architectures such as BERT, which can achieve extremely high accuracy levels (up to ~99% in research settings).

This highlights the importance of moving toward pretrained and large-scale language models in real-world applications.

Conclusion

Spam detection is no longer a simple classification problem—it requires understanding language, context, and intent.

This project demonstrates how different modeling approaches impact performance:

Simple models provide a strong starting point
Sequence models enhance context understanding
Transfer learning delivers state-of-the-art results

The key takeaway:

Better language understanding leads to better spam detection.

Project Link

https://github.com/SinghRaghvendra/DSPortfolio/blob/main/SMS_Spam_Detection_using_TensorFlow_in_Python.ipynb
