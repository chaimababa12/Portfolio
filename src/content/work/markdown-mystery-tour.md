---
title: Offensive Content  and Dialect Detection
publishDate: 2024-01-01
img: /assets/dialect.jpg
img_alt: Overview of the NLP project
description: |
  Developed NLP models to tackle online content moderation challenges, focusing on detecting offensive content and recognizing dialects within Arabic language texts. This project aims to enhance the quality of online interactions by classifying comments based on offensiveness and dialect.

tags:
  - NLP
  - Machine Learning
  - Data Processing
---

## Project Overview

### Context and Objectives

With the rise of social media and online platforms, the way people interact and communicate globally has transformed. This connectivity has led to the creation of virtual dialogue spaces that transcend geographical and cultural boundaries. However, this ease of expression brings challenges such as managing online comments and maintaining a respectful digital environment.

This project focuses on the intersection of technology and online communication by designing and implementing NLP models to address two crucial aspects:

- **Detection of Offensiveness**: Developing a robust NLP model to classify comments based on their level of offensiveness, aiming to proactively moderate harmful content and reduce the risks associated with online hate speech.
- **Dialect Recognition**: Creating a system for effective dialect recognition to enrich contextual understanding of messages, facilitating more precise and respectful communication on digital platforms, with a particular emphasis on the Arabic language.

### Dialect Detection

#### Dataset

- **Training Set**: 12,548 samples
- **Test Set**: 3,000 samples

**Dialect Classes**:

- **Modern Standard Arabic (MSA)**: Standardized Arabic used in media, education, and official documents.
- **Gulf Arabic (Gulf)**: Dialect used in the Gulf region including Saudi Arabia, Bahrain, UAE, Kuwait, Oman, and Qatar.
- **Egyptian Arabic (Egypt)**: Dialect specific to Egypt.
- **Levantine Arabic (Levant)**: Dialect used in Lebanon, Syria, Jordan, Palestine, and Israel.
- **Maghrebi Arabic (Maghreb)**: Dialect used in the Maghreb region including Morocco, Algeria, Tunisia, and Libya.

**Dataset Distribution**:

- **Training Set**: Includes distribution curves for different dialects.
- **Test Set**: Includes distribution curves for different dialects.

#### Data Processing and Preparation

- **Initial Dataset**:

  - **Cleaning**: Removed unnecessary column `dialect_encoded`.
  - **Text Preprocessing**: Cleaned tweet texts by removing emojis and retaining only Arabic words.

- **Preprocessing with ArabERT**: Utilized the ArabERT model to tokenize tweets and obtain phrase embeddings.

#### Model Implementation

- **Model Training**:

  - Trained using ArabERT-generated embeddings and corresponding labels. Logistic Regression was chosen for its simplicity and effectiveness in classification.

- **Model Evaluation**:
  - Evaluated on a validation set with an accuracy of 69%. Further detailed analysis may be required for each specific dialect class.

#### Results

- **Accuracy**: 69%

### Offensive Content Detection

#### Dataset

- **Source**: Arabic Offensive Comments dataset from various social media platforms (Facebook, Twitter, YouTube).
- **Classes**: Offensive and Non-Offensive comments.

#### Data Exploration

- **Non-Offensive**: 730 samples
- **Offensive**: 440 samples

#### Data Processing and Preparation

- **Class Renaming**: Simplified the classification by renaming classes in the `Class` column (e.g., 'abusive' to 'offensive').

- **Tokenizer and ArabERT Model**: Utilized the pre-trained ArabERT model for tokenization and embedding generation.

#### Model Implementation

- **Logistic Regression Model**:
  - Trained with training embeddings and corresponding offensiveness labels.

#### Results

- **Accuracy**: 78.72%

### Enhanced Offensiveness Detection with Dialect Enrichment

- **Objective**: Improve the contextual understanding of offensive comments by incorporating dialect recognition to enhance the overall performance of the detection system.
- **Approach**: Leveraged the previously trained dialect model to identify dialects and refine the offensiveness detection.

<div id="modal" style="display: none; position: fixed; top: 0; left: 0; width: 100%; height: 100%; background-color: rgba(0,0,0,0.8); justify-content: center; align-items: center;">
  <span style="position: absolute; top: 10px; right: 20px; font-size: 2rem; color: white; cursor: pointer;" onclick="closeModal()">&times;</span>
  <button style="position: absolute; left: 10px; top: 50%; font-size: 2rem; color: white; background: none; border: none; cursor: pointer;" onclick="prevImage()">&lt;</button>
  <img id="modal-img" src="" alt="Expanded View" style="max-width: 90%; max-height: 90%;" />
  <button style="position: absolute; right: 10px; top: 50%; font-size: 2rem; color: white; background: none; border: none; cursor: pointer;" onclick="nextImage()">&gt;</button>
</div>

<script>
  const images = [
    '/assets/nlp-screenshot1.png',
    '/assets/nlp-screenshot2.png'
  ];

  let currentIndex = 0;

  function openModal(index) {
    currentIndex = index;
    document.getElementById('modal-img').src = images[currentIndex];
    document.getElementById('modal').style.display = 'flex';
  }

  function closeModal() {
    document.getElementById('modal').style.display = 'none';
  }

  function prevImage() {
    currentIndex = (currentIndex > 0) ? currentIndex - 1 : images.length - 1;
    document.getElementById('modal-img').src = images[currentIndex];
  }

  function nextImage() {
    currentIndex = (currentIndex < images.length - 1) ? currentIndex + 1 : 0;
    document.getElementById('modal-img').src = images[currentIndex];
  }
</script>
