# Facebook Thailand Engagement Analysis
![Facebook onboarding and engagement](/image-TRzMixEGl-transformed.png)
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

## Technologies Used
- Python for all computations and data manipulation.
- Libraries: Pandas, NumPy for data handling; Matplotlib, Seaborn for visualization; Scikit-learn for PCA, clustering, and regression.


Welcome to our comprehensive analysis of Facebook interactions in Thailand! We delve into how different types of content—photos, videos, and text—impact user engagement. Our tools include Principal Component Analysis (PCA), clustering, and logistic regression to uncover trends that can shape effective social media strategies. Our dataset consists of individual Facebook posts, featuring various engagement metrics:

- **Types of Posts**: Photos, videos, and text.
- **Engagement Metrics**: Comments, shares, likes, loves, and more.
- **Time Stamps**: When each post was published.

## Data Preparation

Data preparation is crucial for accurate analysis. We handle missing values and standardize features to ensure consistency across the dataset:

```python
# Standardizing the dataset
df_scaled = unsupervised_scaler(df[['num_comments', 'num_shares', 'num_likes', ...]])
```

## Exploratory Data Analysis (EDA)

Our initial exploration focuses on understanding the distribution of post types and their correlation with engagement metrics:

```python
# Analyzing post types distribution
print(df['status_type'].value_counts(normalize=True))

# Visualizing correlations between engagement metrics
sns.heatmap(df[engagement_metrics].corr(), annot=True, cmap='coolwarm')
```

We discover that photos dominate the dataset, making up 61% of the posts. Videos, though fewer, generate significantly higher engagement across all metrics.

## Principal Component Analysis (PCA)

To reduce dimensionality and focus on the most impactful features, we apply PCA:

```python
# Conducting PCA
pca = PCA(n_components=3)
pca_results = pca.fit_transform(df_scaled)
scree_plot(pca)
```

The scree plot suggests that three components explain most of the variance, providing a simplified yet powerful representation of our data.

## Clustering with K-Means

Identifying clusters within our data helps us understand distinct patterns of engagement:

```python
# Finding optimal cluster count
elbow_plot(range(1, 11), inertias)

# Applying K-Means Clustering
kmeans = KMeans(n_clusters=4)
df['cluster'] = kmeans.fit_predict(pca_results)
```

Analysis reveals four unique clusters, each representing a different engagement pattern, from "Low Engagement" to "High General Engagement."

## Model Development: Logistic Regression

We build logistic regression models to predict the likelihood of a post being a photo based on engagement metrics:

```python
# Logistic regression using original, PCA, and cluster features
model1 = LogisticRegression().fit(X_train, y_train)
model2 = LogisticRegression().fit(X_train_pca, y_train)
model3 = LogisticRegression().fit(X_train_clusters, y_train)
```

Each model's performance is assessed, with the original features model showing the best ability to differentiate photo from non-photo posts based on engagement.

![Engagement Insights](https://github.com/abdullateefokuboye/Facebook-Thailand-Engagement-Analysis/blob/main/Screenshot%202024-04-28%20171346%20(2).png)
## Insights and Actionable Strategies

Our analysis leads to actionable insights:

- **Videos Drive Higher Engagement**: Despite their lower frequency, videos garner more comments, shares, and reactions.
- **Photos Attract Likes and Loves**: While less interactive, photos receive significant 'likes' and 'loves', suggesting they are well-received passively.
- **Text Posts are Least Engaging**: Despite their potential for detailed expression, text posts lag behind in user interaction.

## Conclusion

Leveraging these insights, businesses can tailor their content strategies to maximize engagement on Facebook, optimizing for the types of interactions that best suit their goals. Our analysis not only aids in strategic decision-making but also highlights the power of data-driven approaches in digital marketing. Detailed codes, comments, and visualizations can be found [here](https://github.com/abdullateefokuboye/Facebook-Thailand-Engagement-Analysis)

## Acknowledgments
- This project is inspired by real-world data analysis tasks in social media marketing.
- All thanks for datasets provided for educational purposes.
