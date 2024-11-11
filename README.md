This architecture is designed to analyze the impact of financial news on stock market indices through a three-stage process: sentiment analysis, industry
classification, and impact assessment. The system processes financial news articles, determines their sentiment and industry relevance, and then correlates this
information with historical index data to assess the news’ impact on market trends.

Architecture Components and Flow
1. Data Ingestion Layer
• Dataset to train sentiment analysis models: https://www.kaggle.com/datasets/ankurzing/sentiment-analysis-for-financial-news
• Gathers historical index data from Angel One Smartapi
  Sentiment Analysis Module
    • Preprocesses news articles
        for non-ML models: 
        for ML models: tokenization, stop word removal
    • Employs multiple sentiment analysis models:
    – Lexicon-based: VADER, FINVADER
    – Machine Learning: SVM, CATBOOST
    – Deep Learning: FinBERT
    • Outputs sentiment scores for each news article
Selected FinBERT for the highest accuracy of 89%.

2. Industry Classification Module
  The lexicon-based classification was done since no existing dataset was found to train a model.
  classification categories: IT, Metal, Auto, Bank, Oil and Gas, FMCG, Financial Services, Media, Pharmaceutical, Realty, Healthcare, Consumer Durables, Others
  Assign industry categories to each news article

3. Data Integration Layer
  Combines outputs from Sentiment scores of specific industries with historical data of the inde

4. Impact Assessment Module using time-series analysis
   dataset for final analysis with title and date: https://www.kaggle.com/datasets/hkapoor/indian-financial-news-articles-20032020
  • Utilizes time series analysis techniques LSTM to model
  relationships between:
  – Sentiment scores
  – Industry classifications
  – Historical index movements
  • Generates impact assessments and predictions for different industries and overall market trends


