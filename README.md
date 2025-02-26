# INN Hotels: Predicting Booking Cancellations
This repository contains the complete analysis and predictive modeling work aimed at forecasting booking cancellations for INN Hotels. High cancellation rates have a significant impact on revenue, operations, and customer satisfaction. By leveraging data-driven insights, the project helps INN Hotels mitigate risks through proactive cancellation management and improved policy design.

## Table of Contents

- [Overview](#overview)
- [Data Description](#data-description)
- [Project Structure](#project-structure)
- [Environment & Installation](#environment--installation)
- [Analysis & Modeling](#analysis--modeling)
  - [Exploratory Data Analysis (EDA)](#exploratory-data-analysis-eda)
  - [Data Preprocessing & Feature Engineering](#data-preprocessing--feature-engineering)
  - [Predictive Modeling](#predictive-modeling)
- [Key Findings & Business Recommendations](#key-findings--business-recommendations)
- [License](#license)

## Overview

INN Hotels Group faces significant challenges due to a high rate of booking cancellations. Cancellations lead to revenue loss, additional marketing costs, and operational inefficiencies. The objective of this project is to build a predictive model using historical booking data that forecasts cancellations, thereby allowing the hotel to adjust policies and pricing strategies in advance.

## Data Description

The primary dataset is provided in the file `INNHotelsGroup (1).csv` and contains 19 attributes detailing each booking. Key features include:

- **no_of_adults** and **no_of_children**: Number of adults and children per booking.
- **no_of_weekend_nights** and **no_of_week_nights**: Duration of stay.
- **type_of_meal_plan**: Meal plan selected by the guest.
- **required_car_parking_space**: Indicator for parking space requirements.
- **room_type_reserved**: Encoded room type.
- **lead_time**: Days between booking and arrival.
- **arrival_year, arrival_month, arrival_date**: Arrival information.
- **market_segment_type**: Booking channel or market segment.
- **repeated_guest**: Whether the guest is a repeat customer.
- **no_of_previous_cancellations** and **no_of_previous_bookings_not_canceled**: Customer booking history.
- **avg_price_per_room**: Dynamic room pricing.
- **no_of_special_requests**: Special requests made by the guest.
- **booking_status**: Cancellation flag (target variable; 1 if canceled, 0 otherwise).

## Project Structure

```
INN-Hotels-Predicting-Cancellations/
├── INNHotelsGroup (1).csv      # Booking dataset
├── INN Hotels Project Code.pdf        # Detailed code and analysis report
├── INN Hotels Project PowerPoint Presentation.pdf  # Presentation with key insights and recommendations
├── LICENSE
└── README.md                      # This file
```

## Environment & Installation

To replicate the analysis, ensure you have Python 3.x installed along with the following libraries:
- numpy
- pandas
- matplotlib
- seaborn
- scikit-learn
- statsmodels

## Analysis & Modeling

### Exploratory Data Analysis (EDA)

The initial EDA focused on understanding the booking patterns and identifying key variables:
- **Univariate Analysis**: Distribution of key features such as lead time, average room price, and number of special requests.
- **Bivariate Analysis**: Examining relationships between predictors (e.g., lead time, market segment, special requests) and the cancellation status.

### Data Preprocessing & Feature Engineering

Key preprocessing steps included:
- **Data Cleaning**: Removal of duplicates and irrelevant identifiers (e.g., Booking_ID).
- **Outlier Treatment**: Capping extreme values (e.g., average room price) using the IQR method.
- **Feature Engineering**: Creating new features like total stay duration and price-per-night, as well as encoding categorical variables using dummy variables.
- **Standardization**: Scaling continuous features to balance their influence during modeling.

### Predictive Modeling

Two models were developed and evaluated:
- **Logistic Regression**: Served as the baseline model with interpretable coefficients. Key predictors include lead time, number of special requests, repeated guest status, and market segment.
- **Decision Tree Classifier**: Provided additional insights through decision rules (e.g., long lead times and low special requests increase cancellation risk). Although more complex, the decision tree model was more prone to overfitting.

Evaluation metrics included accuracy, precision, recall, F1-score, and AUC-ROC. The logistic regression model was selected as the final model due to its interpretability, balanced performance, and lower risk of overfitting.

## Key Findings & Business Recommendations

- **Lead Time**: Bookings made well in advance (e.g., >90 days) have significantly higher cancellation rates.
- **Special Requests**: A higher number of special requests correlates with a lower chance of cancellation, suggesting increased customer commitment.
- **Market Segment**: Online bookings exhibit a higher cancellation rate compared to corporate or offline channels.
- **Repeated Guests**: Repeat customers are much less likely to cancel their bookings.

**Business Recommendations:**
- Introduce partial prepayment for bookings with long lead times.
- Encourage guests to provide special requests through incentives.
- Implement stricter cancellation policies for online bookings.
- Expand loyalty programs to retain low-risk, repeat customers.
- Adjust dynamic pricing strategies to account for cancellation risks based on booking characteristics.

## License

This project is licensed under the MIT License – see the [LICENSE](./LICENSE) file for details.
