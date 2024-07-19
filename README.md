# Cold Start Challenge in Recommendation Systems: A Deep Learning Approach

This repository contains the implementation of a hybrid model that integrates Deep Neural Networks (DNN) with Alternating Least Squares (ALS) for addressing the cold start challenge in recommendation systems, specifically for recommending restaurants to new users with no interaction history.

## Overview

The goal of this project is to enhance the ability to predict user preferences in the absence of rating history by developing a hybrid model. This model leverages implicit data such as restaurant ratings and rating counts to refine the user-item matrix more effectively compared to using ALS alone. The integration of ALS and DNN in our hybrid model has shown promising results in overcoming the limitations of traditional recommendation system approaches, particularly in handling cold-start scenarios.

This is a course project for ST446 Distributed Computing for Big Data.

## Data

### Strategy of Data Processing

To address the cold-start problem in ALS model, we used Google Local Data (2021), which encompasses review details from Google Maps up to September 2021 in the United States. This dataset includes rating data, such as ratings and timestamps, alongside business metadata, like addresses, review counts, and categories. The database predominantly comprises users with limited historical data where most users have provided only one rating. This characteristic closely aligns with our research question and mirrors the real-world scenario where the platform frequently needs to generate recommendations for new users without knowing their preferences. With its extensive data volume of over 600 million ratings from 100 million users, this database serves as an appropriate choice for the project, providing a comprehensive and realistic representation of the challenges associated with recommendation systems.

To deal with the extensive data, we employed distributed computing using Google Cloud Platform (GCP) for data storage and processing. Parquet, seamlessly integrated with Apache Spark, leverages partitioned and columnar storage to enhance the performance of data query and retrieval effectively.

## Models Implemented

### Hybrid Model (DNN + ALS)

The hybrid model combines Deep Neural Networks (DNN) with Alternating Least Squares (ALS) to predict user preferences. This approach aims to address the cold start problem by integrating the strengths of both methods.

#### Key Features:
- Achieved an average precision of 89% for cold start users
- Combines deep learning with ALS to improve recommendation accuracy
- Leverages implicit data (restaurant ratings and rating counts) for better user-item matrix refinement
- Outperformed ALS-only models by 2% for non-cold start users when using 10% and 20% data

## Results

The hybrid model demonstrated superior performance, achieving a PR-AUC value of 0.89 on user cold start data and generally performing better on cold start than non-cold start data by a margin of 0.05 to 0.07. The model yielded better outcomes across datasets of both 10% and 20% compared to ALS only, indicating its effectiveness in addressing the cold-start user problem and enhancing overall recommendation quality in real-world scenarios.

## Repository Structure

- `Code/`: Contains the implementation of data preprocessing, ALS, and the hybrid model (DNN + ALS).

- `Developing Deep Learning Model for Cold Start Challenge in Recommendation Systems.pdf`: Comprehensive analysis report.
