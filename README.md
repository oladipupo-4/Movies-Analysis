# Exploring Trends in the Movie Industry using the TMDB 5000 Dataset

## Project Overview

This project explores trends and patterns in the movie industry using the TMDB 5000 Movie Dataset. The analysis covers various aspects, including the relationship between budget and revenue, genre popularity and profitability, and the correlation between movie popularity and ratings. The goal is to gain insights into the factors that contribute to a movie's success and understand the dynamics of the film industry.

## Dataset Source

The TMDB 5000 Movie Dataset was obtained from [Kaggle](https://www.kaggle.com/datasets/tmdb/tmdb-movie-dataset). It contains information about 5000 movies, including their titles, genres, release dates, budgets, revenues, popularity scores, vote averages, and more.

## Data Cleaning and Preprocessing

The dataset required several cleaning and preprocessing steps before analysis:

* **Missing Values:** Several columns had missing values.
    * 'homepage', 'overview', and 'tagline': Missing values were filled with placeholder text (e.g., "No Homepage Provided").
    * 'release_date': Missing dates were filled with 'Unknown' after converting the column to datetime objects.
    * 'runtime': Missing values were replaced with 0.
    * 'budget': Missing budget values (represented by dashes) were treated as "Undisclosed" and assigned the value -1.
* **Budget Data:** The 'budget' column was cleaned by removing currency symbols and commas and converting it to a numeric type. Missing budget values were handled as described above.
* **Genre Data:** The 'genres' column, which contained stringified lists of dictionaries, was transformed by:
    1. Converting the strings to lists using `eval()`.
    2. Extracting the genre names from the dictionaries.
    3. Exploding the DataFrame so each movie had one row per genre.

## Exploratory Data Analysis (EDA)

The exploratory data analysis focused on:

* **Descriptive Statistics:** Summary statistics (mean, median, standard deviation, etc.) were calculated for numerical variables.
* **Histograms:** Histograms visualized the distribution of 'budget', 'revenue', 'popularity', 'vote_average', and 'runtime'.
* **Scatter Plots:** Scatter plots explored the relationships between 'budget' and 'revenue', and 'popularity' and 'vote_average'. Regression lines were added.
* **Correlation Matrix:** A correlation matrix (heatmap) visualized linear relationships between numerical variables.
* **Grouped Analysis:** The data was grouped by genre to analyze popularity and average vote.

## Key Findings and Insights

* **Budget vs. Revenue:** A strong positive correlation was observed between budget and revenue (0.73). Higher-budget movies tend to generate higher revenues, but the relationship isn't perfect, indicating other influential factors.
* **Popularity vs. Vote Average:** A moderate positive correlation was found between popularity and vote average (correlation coefficient: (0.27). More popular movies tend to receive slightly higher ratings, but the relationship is not as strong as budget vs. revenue.  This suggests that while popularity can be an indicator of overall audience sentiment, it doesn't guarantee critical acclaim.
* **Genre Trends:**  
With Drama having a popularity of 5091.126 and Comedy having a popularity of 4758.276, this shows the top 2 most popular genres. With Horror coming in next with popularity of 1118.065.
Movies with "Music", "Adventure", "Animation", "Action", "Comedy" genres have an average vote of 6.6.
Genre Combinations: Combining genres can affect popularity. For example, "Drama" combined with "Romance" has a lower popularity than "Drama" alone. This could be due to a more niche audience.
* **Word-of-Mouth Influence:** The relationship between popularity and vote average suggests that positive word-of-mouth can contribute to higher ratings, but hype doesn't always translate to critical acclaim.  Movies can be popular without being universally loved.

## Code Explanation

The code for this project is in the Jupyter Notebook `movie_analysis.ipynb`. The notebook is organized as follows:

1. Data Loading and Cleaning
2. Exploratory Data Analysis
3. Visualization
4. Insights and Storytelling

## Challenges Faced

* **Missing Data:** Handling missing values, especially in the 'budget' column, required careful consideration. The chosen strategy was to treat missing budget values as "Undisclosed" (-1) and fill other missing values with placeholders or appropriate values.
* **Genre Data Cleaning:** Cleaning and transforming the 'genres' column, which contained complex nested data structures, was a significant challenge.

## Conclusion and Future Work

This project provided valuable insights into the movie industry. Future work could explore the impact of directors, actors, production companies, or marketing campaigns. Sentiment analysis of movie reviews could also be insightful.

## Requirements

The project uses the following Python libraries:

* pandas
* matplotlib
* seaborn
* numpy

## Author

Onibon Oladipupo