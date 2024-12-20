# ChatGPT Reviews Analysis

## Overview
This project analyzes user reviews of ChatGPT to understand sentiment trends, identify recurring issues, and provide actionable insights. By leveraging Natural Language Processing (NLP) techniques and time-series analysis, it evaluates user satisfaction and highlights opportunities for improving the user experience.

## Objectives
- **Sentiment Analysis:** Classify reviews into positive, neutral, and negative sentiments.
- **Time-Series Analysis:** Track how sentiment evolves over time to understand trends.
- **Net Promoter Score (NPS):** Calculate NPS to measure user loyalty and willingness to recommend ChatGPT.
- **Issue Identification:** Extract recurring problems from negative reviews for targeted improvements.

## Key Features
- **Sentiment Classification:** Classify reviews into sentiment categories using TextBlob and NLP techniques.
- **Keyword Extraction:** Identify frequently mentioned phrases and words in positive and negative reviews.
- **Visualization:** Generate visual insights into sentiment distribution, keyword frequency, and sentiment trends over time.
- **NPS Calculation:** Assess user loyalty through a calculated Net Promoter Score.

## Technologies Used
- **Programming Language:** Python
- **Libraries and Tools:**
  - `Pandas` and `NumPy` for data preprocessing and analysis.
  - `Matplotlib`, `Seaborn`, and `Plotly` for data visualization.
  - `TextBlob` for sentiment analysis.
  - `CountVectorizer` for keyword and n-gram extraction.
  - `Jupyter Notebook` for running and presenting the analysis interactively.

## Dataset Information
The dataset includes:
- **User Reviews:** Textual feedback from users.
- **Ratings:** Ratings on a 1–5 scale.
- **Review Timestamps:** Dates and times of user reviews for temporal analysis.

### Dataset Challenges:
- Presence of null values in some reviews.
- Imbalanced sentiment distribution with a majority of positive reviews.
- Noisy textual data requiring preprocessing.

## Steps to Reproduce
### 1. Clone the Repository
```bash
git clone https://github.com/KARSarma/ChatGPT-Reviews-Analysis.git
cd ChatGPT-Reviews-Analysis
```

### 2. Set Up the Environment
- Install Python (3.7 or higher).
- Install the required libraries:
  ```bash
  pip install -r requirements.txt
  ```

### 3. Run the Notebook
- Open `ChatGPT_Reviews_Analysis.ipynb` in Jupyter Notebook.
- Execute the cells sequentially to preprocess data, perform sentiment analysis, and generate visualizations.

## Analysis Overview
### Sentiment Analysis
Using `TextBlob`, each review is assigned a sentiment category:
- **Positive:** Polarity > 0
- **Neutral:** Polarity = 0
- **Negative:** Polarity < 0

### Time-Series Analysis
Reviews are aggregated by sentiment category over time to identify trends in user feedback.

### Net Promoter Score (NPS)
- **Promoters:** Users who rated 5 stars.
- **Passives:** Users who rated 4 stars.
- **Detractors:** Users who rated 3 stars or below.
- **NPS Calculation:** `%Promoters - %Detractors`.

### Issue Identification
Negative reviews are analyzed to extract common issues, grouped into broader problem categories:
- **Incorrect Answers**
- **App Performance**
- **Feature Limitations**

## Results and Insights
- **Sentiment Distribution:** 
  - Positive: 70%
  - Neutral: 20%
  - Negative: 10%
- **Sentiment Trends:** Positive reviews increased by 15% over six months, indicating improved user satisfaction.
- **Net Promoter Score (NPS):** 64.35, reflecting strong user loyalty.
- **Key Issues:** Common complaints include incorrect answers, app glitches, and usability concerns.

## Visualizations
1. **Sentiment Distribution:** Bar chart of positive, neutral, and negative reviews.
2. **Trends Over Time:** Line chart illustrating sentiment evolution over time.
3. **Top Keywords:** Word cloud and bar chart showcasing frequently mentioned phrases.
4. **Common Problems:** Bar chart of top issues derived from negative reviews.

## Sample Code
### Sentiment Analysis
```python
from textblob import TextBlob

def analyze_sentiment(text):
    analysis = TextBlob(text)
    if analysis.sentiment.polarity > 0:
        return 'Positive'
    elif analysis.sentiment.polarity == 0:
        return 'Neutral'
    else:
        return 'Negative'

data['Sentiment'] = data['Review'].apply(analyze_sentiment)
```

### Sentiment Visualization
```python
import matplotlib.pyplot as plt
import seaborn as sns

sns.countplot(x='Sentiment', data=data)
plt.title('Sentiment Distribution')
plt.xlabel('Sentiment')
plt.ylabel('Number of Reviews')
plt.show()
```

## Contribution Guidelines
We welcome contributions to enhance this project! To contribute:
1. Fork the repository.
2. Create a new branch for your feature or bug fix:
   ```bash
   git checkout -b feature-name
   ```
3. Commit your changes:
   ```bash
   git commit -m "Add feature-name"
   ```
4. Push to your branch:
   ```bash
   git push origin feature-name
   ```
5. Open a pull request.

## License
This project is licensed under the MIT License. See the [LICENSE](LICENSE) file for more details.

## Contact
For questions or feedback, feel free to contact **Anirudha Kuchibhotla** at [anirudha.kuchibhotla@gmail.com]

