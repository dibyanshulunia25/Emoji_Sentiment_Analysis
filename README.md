# 📊 Emoji Sentiment Analysis Project

![Python](https://img.shields.io/badge/Python-3.8%2B-blue)
![Pandas](https://img.shields.io/badge/Pandas-1.3+-red)
![Scikit-learn](https://img.shields.io/badge/Scikit--learn-0.24+-orange)
![Matplotlib](https://img.shields.io/badge/Matplotlib-3.4+-blueviolet)

A comprehensive data analysis project that explores the sentiment behind emojis based on their usage in Twitter data across 13 European languages.

## 📋 Project Overview

This project analyzes a dataset of 1.6 million tweets to understand how emojis convey sentiment in digital communication. The research examines whether popular emojis are generally associated with positive or negative sentiments, their placement within tweets, and builds a predictive model to classify emoji sentiment.

## 📊 Dataset Information

The dataset `emoji-sentiment.csv` contains information about emoji usage and sentiment derived from Twitter analysis:

- **Source**: 1.6 million tweets across 13 European languages
- **Emoji-containing tweets**: Approximately 4% of all tweets
- **Annotation**: Each tweet was labeled as positive (+1), negative (-1), or neutral (0)

### Dataset Columns
- `Char`: The emoji character
- `Image [twemoji]`: Visual representation of the emoji
- `Unicode codepoint`: Unicode identifier
- `Occurrences`: Frequency of emoji appearance in the dataset
- `Position`: Average position in tweets (0 = start, 1 = end)
- `Neg`: Percentage of tweets with this emoji that are negative
- `Neut`: Percentage of tweets with this emoji that are neutral
- `Pos`: Percentage of tweets with this emoji that are positive
- `Unicode name`: Official name of the emoji
- `Unicode block`: Category of the emoji

## 🎯 Project Goals

1. Analyze the sentiment distribution of emojis
2. Identify the most positive and negative emojis
3. Examine emoji placement patterns in tweets
4. Build a machine learning model to predict emoji sentiment
5. Visualize relationships between emoji features and sentiment

## 🛠️ Implementation

### Data Preprocessing
- Renamed columns to snake_case for consistency
- Filtered emojis with more than 500 occurrences for meaningful analysis
- Created new features:
  - `Sentiment`: Calculated as Pos% - Neg%
  - `positive_flag`: Boolean indicating positive sentiment (Sentiment > 0)

### Key Findings

#### Most Positive and Negative Emojis
- **Most Positive**: ❤ (Heavy Black Heart) with 79% positive sentiment
- **Most Negative**: 😩 (Weary Face) and 😒 (Unamused Face) with 59.1% negative sentiment each

#### Emoji Placement
- Most emojis are placed toward the **end** of tweets (average position: 0.67)

#### Sentiment Distribution
- 82.4% of all emojis have a positive sentiment
- 90% of the top 20 most popular emojis have positive sentiment

### Machine Learning Model

Built a Decision Tree Classifier to predict whether an emoji has positive sentiment:

- **Features**: Occurrences, Position, Neg%, Neut%, Pos%, Sentiment score
- **Target**: positive_flag (True/False)
- **Performance**:
  - Accuracy: 99.0%
  - Precision: 100%
  - Recall: 98.8%
  - F1-score: 99.4%

## 📈 Visualizations

The project includes several scatter plots to explore relationships between:
- Positive sentiment percentage vs. emoji position
- Negative sentiment percentage vs. emoji position
- Neutral sentiment percentage vs. emoji position
- Emoji position vs. overall sentiment score
- Occurrence frequency vs. sentiment score

## 🚀 How to Run the Project

1. Clone the repository
2. Ensure you have Python 3.8+ installed
3. Install required packages:
   ```bash
   pip install pandas matplotlib scikit-learn
   ```
4. Download the dataset (`emoji-sentiment.csv`)
5. Run the Jupyter notebook or Python script

## 📁 Project Structure

```
emoji-sentiment-analysis/
├── emoji_sentiment_analysis.ipynb  # Main analysis notebook
├── emoji-sentiment.csv            # Dataset
├── requirements.txt               # Project dependencies
└── README.md                      # Project documentation
```

## 🔮 Future Enhancements

Potential improvements for the project:
- Incorporate more advanced visualization techniques
- Experiment with different machine learning models
- Analyze sentiment differences across languages
- Investigate temporal trends in emoji sentiment
- Create an interactive dashboard for exploration

## 📚 References

- Original research: [Emoji Sentiment Ranking](http://kt.ijs.si/data/Emoji_sentiment_ranking/)
- Dataset source: [Emoji Sentiment Data](http://kt.ijs.si/data/Emoji_sentiment_ranking/index.html)

## 👥 Contributing

Contributions to improve the analysis or extend the project are welcome. Please feel free to submit issues or pull requests.

## 📄 License

This project is open source and available under the [MIT License](LICENSE).

---

**Note**: This project is for educational and research purposes. The analysis provides insights into emoji usage patterns but may not represent universal sentiment associations across all contexts and cultures.
