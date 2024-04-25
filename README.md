# Facebook Thailand Engagement Analysis

## Project Overview
This project analyzes Facebook post data from Thailand to understand how different types of content (photos, videos, text) influence user engagement metrics such as likes, shares, comments, and reactions. The analysis incorporates techniques like Principal Component Analysis (PCA), clustering, and logistic regression modeling to provide insights that could inform effective social media marketing strategies.

## Dataset
The dataset consists of various Facebook posts, each characterized by:
- `status_id`: Unique identifier for each post.
- `status_type`: Type of the post (photo, video, text).
- `time_published`: Date and time of post publication.
- Engagement metrics including:
  - `num_comments`: Number of comments.
  - `num_shares`: Number of shares.
  - `num_likes`: Number of 'likes'.
  - Reactions such as 'love', 'wow', 'haha', 'sad', and 'angry'.

## Objectives
- To determine the impact of different post types on engagement metrics.
- To identify patterns and trends in how different content performs in terms of user interaction.
- To suggest content strategies that could enhance engagement based on the findings.

## Methodology
### Data Preprocessing
- Data is cleaned and prepared for analysis, ensuring correct data types and handling missing values if any.

### Exploratory Data Analysis (EDA)
- Distribution of post types and basic descriptive statistics to understand the dataset's composition.
- Visualization of engagement metrics to identify trends and outliers.

### Advanced Analysis
- **PCA**: Used to reduce dimensionality of the dataset and to identify underlying variables influencing engagement.
- **Clustering (K-Means)**: To segment the posts based on engagement patterns.
- **Logistic Regression**: To model the probability of a post being a photo based on engagement metrics.

## Technologies Used
- Python for all computations and data manipulation.
- Libraries: Pandas, NumPy for data handling; Matplotlib, Seaborn for visualization; Scikit-learn for PCA, clustering, and regression.

## Key Findings
- Videos tend to have higher engagement in terms of comments and shares.
- Photos generally receive more 'likes' and 'loves', indicating a positive reception but lower interactive engagement compared to videos.
- Text posts, while less frequent, can still garner significant engagement, particularly in terms of likes.

## Acknowledgments
- This project is inspired by real-world data analysis tasks in social media marketing.
- All thanks for datasets provided for educational purposes.
