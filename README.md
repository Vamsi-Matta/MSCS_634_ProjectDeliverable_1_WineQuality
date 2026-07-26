# Repository-MSCS_634_ProjectDeliverable_1_WineQuality

# MSCS 634 — Project Deliverable 1  
## NYC Airbnb Data Collection, Cleaning, and Exploration

## Project Overview

This project prepares and explores the New York City Airbnb 2019 dataset for future data-mining tasks.

The dataset contains Airbnb listing information such as location, room type, nightly price, minimum stay, review activity, host portfolio size, and annual availability.

The analysis focuses on data validation, missing-value treatment, duplicate detection, noisy-data correction, outlier management, feature engineering, and exploratory data analysis.

## Dataset Summary

The original dataset contains:

- 48,895 records
- 16 attributes
- Five New York City borough groups
- Numerical, categorical, text, date, and geographic variables

Important attributes include:

- Listing and host identifiers
- Borough and neighborhood
- Latitude and longitude
- Room type
- Nightly price
- Minimum nights
- Number of reviews
- Reviews per month
- Host listing count
- Annual availability

## Dataset Selection Justification

The dataset was selected because it:

- Exceeds the requirement of 500 records
- Contains more than 10 attributes
- Includes genuine missing values
- Contains noisy and extreme numerical observations
- Supports useful exploratory visualizations
- Can support regression, classification, clustering, and association-rule mining in later deliverables

## Data Cleaning Steps

The following cleaning steps were completed:

1. Validated the expected dataset schema.
2. Inspected data types and record completeness.
3. Replaced missing listing names with `Unnamed Listing`.
4. Replaced missing host names with `Unknown Host`.
5. Replaced missing `reviews_per_month` values with zero.
6. Converted `last_review` into datetime format.
7. Preserved missing review dates when no review history existed.
8. Checked exact duplicate rows.
9. Checked repeated listing IDs.
10. Inspected repeated listing profiles.
11. Standardized whitespace in text attributes.
12. Removed listings with zero or negative prices.
13. Validated minimum nights, reviews, availability, latitude, and longitude.
14. Detected potential outliers using the IQR method.
15. Controlled extreme values through first- and ninety-ninth-percentile capping.

## Feature Engineering

The following features were created:

- `price_category`
- `review_status`
- `availability_level`
- `host_activity`

These features support interpretation and future modeling.

## Exploratory Data Analysis

The notebook includes visualizations of:

- Missing values
- Price distribution before and after treatment
- Minimum-night distribution
- Outlier counts
- Price boxplots
- Listing counts by borough
- Room-type distribution
- Price-category distribution
- Review status
- Availability levels
- Price by borough
- Price by room type
- Top neighborhoods
- Geographic listing distribution
- Average price by borough and room type
- Host activity
- Numerical correlations
- Review count and price
- Neighborhood median prices
- Multivariable feature relationships

## Key Findings

The analysis showed that:

- Listings are concentrated in selected boroughs and neighborhoods.
- Room type is strongly associated with nightly price.
- Price is highly right-skewed.
- Review count alone does not clearly explain price.
- Availability differs substantially across listings.
- Host portfolio size creates distinct listing groups.
- Numerical correlations with price are generally weak.
- Categorical and geographic features are likely to be important in future models.

## Challenges and Solutions

### Missing review information

Many listings had no review date or monthly review rate.

**Solution:** Monthly review values were replaced with zero, while missing dates were preserved because they may represent listings without reviews.

### Extreme numerical values

Price, minimum nights, reviews, and host listing count contained unusually large observations.

**Solution:** Outliers were identified with IQR and treated using percentile capping rather than deleting all unusual listings.

### Large visualizations

The dataset contains nearly 49,000 observations.

**Solution:** Reproducible samples were used for dense scatter plots and pair plots.

### Weak linear correlations

Several numerical variables had weak correlations with price.

**Solution:** Grouped analysis, boxplots, geographic plots, and categorical comparisons were used alongside correlation analysis.

