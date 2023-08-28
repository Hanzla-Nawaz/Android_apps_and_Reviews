# Google Play Store apps and reviews

This repository contains code for analyzing data related to Google Play Store apps and their reviews. The dataset consists of two files: `apps.csv` and `user_reviews.csv`.

## Data Read and Cleaning

The `apps.csv` file contains details of various applications on Google Play Store, and the `user_reviews.csv` file contains user reviews for each app. Here's how the data is read and cleaned:

1. **Data Read**
    ```python
    import pandas as pd
    import warnings
    warnings.simplefilter("ignore", UserWarning)
    apps_with_duplicates = pd.read_csv("apps.csv")
    ```

2. **Removing Duplicates**
    ```python
    apps = apps_with_duplicates.drop_duplicates()
    ```

## Data Cleaning

Special characters in the `Installs` and `Price` columns are removed, and columns are converted to appropriate data types.

```python
chars_to_remove = ['+', ',', '$']
cols_to_clean = ['Installs', 'Price']

for col in cols_to_clean:
    for char in chars_to_remove:
        apps[col] = apps[col].apply(lambda x: x.replace(char, ''))
        
apps['Installs'] = pd.to_numeric(apps['Installs'], errors='coerce')
apps['Price'] = pd.to_numeric(apps['Price'], errors='coerce')
Exploratory Data Analysis
App Categories
The distribution of app categories is analyzed using a bar chart.
App Categories

App Ratings Distribution
The distribution of app ratings is visualized using a histogram.
App Ratings

Size and Price Analysis
The relationship between app size and rating, as well as price and rating, is explored using scatter plots.
Size vs Rating
Price vs Rating

App Pricing Trend
The pricing trend across different app categories is examined.
App Pricing Trend

Popularity of Paid vs Free Apps
A box plot is used to compare the number of app installs for paid and free apps.
Paid vs Free Apps

Sentiment Analysis of User Reviews
Sentiment polarity scores of user reviews for paid and free apps are visualized using box plots.
Sentiment Analysis

Conclusion
This code provides insights into the Google Play Store apps and their reviews. The analysis covers app categories, ratings, size, price, popularity, and sentiment analysis. The findings can be used to make informed decisions when developing and pricing apps on the Google Play Store.# Google Play Store apps and reviews

This repository contains code for analyzing data related to Google Play Store apps and their reviews. The dataset consists of two files: `apps.csv` and `user_reviews.csv`.

## Data Read and Cleaning

The `apps.csv` file contains details of various applications on Google Play Store, and the `user_reviews.csv` file contains user reviews for each app. Here's how the data is read and cleaned:

1. **Data Read**
    ```python
    import pandas as pd
    import warnings
    warnings.simplefilter("ignore", UserWarning)
    apps_with_duplicates = pd.read_csv("apps.csv")
    ```

2. **Removing Duplicates**
    ```python
    apps = apps_with_duplicates.drop_duplicates()
    ```

## Data Cleaning

Special characters in the `Installs` and `Price` columns are removed, and columns are converted to appropriate data types.

```python
chars_to_remove = ['+', ',', '$']
cols_to_clean = ['Installs', 'Price']

for col in cols_to_clean:
    for char in chars_to_remove:
        apps[col] = apps[col].apply(lambda x: x.replace(char, ''))
        
apps['Installs'] = pd.to_numeric(apps['Installs'], errors='coerce')
apps['Price'] = pd.to_numeric(apps['Price'], errors='coerce')
Exploratory Data Analysis
App Categories
The distribution of app categories is analyzed using a bar chart.
App Categories

App Ratings Distribution
The distribution of app ratings is visualized using a histogram.
App Ratings

Size and Price Analysis
The relationship between app size and rating, as well as price and rating, is explored using scatter plots.

App Pricing Trend
The pricing trend across different app categories is examined.
App Pricing Trend

Popularity of Paid vs Free Apps
A box plot is used to compare the number of app installs for paid and free apps.

Sentiment Analysis of User Reviews
Sentiment polarity scores of user reviews for paid and free apps are visualized using box plots.
Sentiment Analysis

Conclusion
This code provides insights into the Google Play Store apps and their reviews. The analysis covers app categories, ratings, size, price, popularity, and sentiment analysis. The findings can be used to make informed decisions when developing and pricing apps on the Google Play Store.
