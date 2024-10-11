# Sentiment Analysis with IMDb Reviews

This project involves performing sentiment analysis on IMDb movie reviews, classifying them as either positive or negative using various machine learning models.

## Dataset

The dataset contains movie reviews labeled as either `positive` or `negative`. It was sourced from [Google Drive](https://drive.google.com/drive/folders/1pRqSmSCXtB4BBlk6EmgkgnlHsz6_azG6).

## Project Workflow

1. **Preprocessing:**
   - The text data was cleaned by removing HTML tags, expanding contractions, and eliminating punctuations, stopwords, and emojis.
   - Lemmatization was applied to reduce words to their root forms, making the data more uniform for analysis.

2. **Exploratory Data Analysis (EDA):**

   ### Frequencies of Sentiment Labels
   <div align="center">
   <img src="https://raw.githubusercontent.com/hiephoangt/Sentiment_Analysis_With_IDBM/main/Image/Frequencies%20of%20Sentiment%20Labels.jpg" alt="Frequencies of Sentiment Labels" width="400">
   </div>

   **Insight:**  
   From the pie chart, we observe that the dataset is relatively balanced, with a slight skew towards positive reviews. The balanced nature of the dataset ensures that machine learning models won’t be biased toward one class, which is important for ensuring robust and fair predictions. This balance provides confidence that classifiers will perform reasonably well for both positive and negative sentiments without significant bias toward one category.

   ### Word Length Analysis for Positive and Negative Reviews

   **Positive Reviews:**
   <div align="center">
   <img src="https://raw.githubusercontent.com/hiephoangt/Sentiment_Analysis_With_IDBM/main/Image/Word%20Length%20In%20Positive%20Review.jpg" alt="Word Length of Positive Reviews" width="400">
   </div>

   **Negative Reviews:**
   <div align="center">
   <img src="https://raw.githubusercontent.com/hiephoangt/Sentiment_Analysis_With_IDBM/main/Image/Word%20Length%20In%20Negative%20Review.jpg" alt="Word Length of Negative Reviews" width="400">
   </div>

   **Insight:**  
   The histograms reveal that while some reviews have very short lengths, the majority fall within the 0 to 1400-word range. This suggests that detailed reviews exist alongside more concise ones. To optimize our feature representation, using TfidfVectorizer with a max_features limit of 5000 is appropriate.

3. **Data Splitting:**
   - The dataset was split into training and testing sets in an 80-20 ratio, ensuring the model is trained on a large portion of the data while reserving a portion for model validation.

4. **Text Encoding:**
   - The reviews were transformed into a numerical format using the TF-IDF vectorizer with a maximum feature limit of 5000, capturing the most relevant words while reducing the impact of less informative terms.

5. **Model Training and Evaluation:**
   Multiple machine learning models were trained on the data, and their accuracy scores were computed:

   - **Decision Tree:**  
     Accuracy: `71.45%`
   - **Random Forest:**  
     Accuracy: `84%`
   - **AdaBoost:**  
     Accuracy: `83%`
   - **Gradient Boosting:**  
     Accuracy: `81%`
   - **XGBoost:**  
     Accuracy: `86%`

## Conclusion

The models trained in this project demonstrated robust sentiment classification, with XGBoost achieving the highest accuracy at 86%. The effectiveness of ensemble methods such as Random Forest, AdaBoost, and XGBoost highlights their capability in handling this type of classification task effectively.
