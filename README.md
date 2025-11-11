# Predicting TV Series Renewal

Project Renewal Predictor: Predicting TV Show Renewals

This project delivers a machine learning model designed to forecast whether a television series will be renewed for another season or canceled based on its metadata and performance metrics.

--------------------------------------------------------------------------------

1. Table of Contents

* Overview & Business Context
* Dataset & Features
* Installation & Usage
* Model & Performance

2. Overview & Business Context

Media networks and production studios face a high-stakes challenge: determining which TV series to renew or cancel. These decisions carry significant financial risk, impacting everything from production budgets to marketing strategy. This project directly addresses that challenge by developing a predictive model to forecast series longevity, mitigating financial exposure and maximizing return on content investment.

* Business Value: This predictive model addresses a core business problem by providing a data-driven framework to support these critical decisions. By analyzing historical data, the model can help stakeholders identify series with a high probability of success, justifying further investment in production and marketing. Conversely, it can flag underperforming shows early, enabling networks to mitigate financial losses by canceling them before committing to another costly season.
* Research Question:

Can a machine learning model accurately predict whether a TV series will be renewed for another season or be canceled, based on its available metadata and performance metrics?

This project leverages a comprehensive dataset to answer this question and build a reliable predictive tool.

3. Dataset & Features

The predictive power of any machine learning model is fundamentally dependent on the quality and richness of its input data. The model developed in this project was trained on a detailed dataset of television series, from which key predictive features were identified and engineered. This section details the data source, the most influential features, and the essential preprocessing steps performed.

* Data Source: The model was trained and validated on a comprehensive TV series dataset sourced from The Movie Database (TMDB). The initial raw dataset contained 168,639 records and 29 distinct features before cleaning and preprocessing.
* Key Predictive Features: Through statistical analysis (ANOVA F-scores), several features emerged as the most powerful signals for predicting a show's renewal status. The most influential predictors included:
  * series_age: The number of years a show has been on the air. As the strongest chronological predictor, it reflects an established viewership and higher likelihood of renewal.
  * Audience Engagement Metrics (popularity_log, vote_count_log): These log-transformed metrics were among the top-performing indicators of audience engagement and viewership volume, serving as direct signals of a show's market traction.
  * overview_words: The word count of the show's summary, which acts as a powerful proxy for the richness of provided metadata and, by extension, the show's content maturity.
* Preprocessing Summary: A series of critical data preparation steps were executed to ensure the data was clean, consistent, and ready for modeling. This included the imputation of missing values, the strategic grouping of rare categorical variables into a unified 'Other' category to reduce noise, and the final conversion of all categorical features into a numerical format using One-Hot Encoding.

This carefully prepared dataset forms the foundation for running the project and training the predictive model.

4. Installation & Usage

These instructions provide a step-by-step guide for setting up the necessary environment and running the project's analytical notebooks.

* Prerequisites:
  * Python 3.9+
  * pip (Python package installer)
* Dependencies: Install the required Python libraries by running the following command in your terminal. These packages provide the core functionalities for data manipulation, machine learning, and visualization used in the project.
* Running the Project: The analysis is segmented across several Jupyter notebooks that cover the end-to-end machine learning pipeline (e.g., Data Preparation, Exploratory Data Analysis, Modeling). To launch the project environment, navigate to the project's root directory in your terminal and run:
* This will open the Jupyter interface in your web browser, where you can open and execute the notebooks in sequence.

Once the environment is operational, the notebooks can be executed to reproduce the analysis, which culminates in the high-performance model detailed below.

5. Model & Performance

After systematically evaluating multiple algorithms, the project yielded a definitive, high-performing model. This section details the winning algorithm, the rigorous evaluation process, and its final, validated performance on unseen holdout data.

* Core Algorithm: The final predictive model is a RandomForestClassifier. This ensemble algorithm was selected based on its quantifiably superior performance in cross-validation. During 3-fold cross-validation, the RandomForestClassifier achieved a mean ROC-AUC of 0.9249, decisively outperforming other candidates such as K-Nearest Neighbors (0.9056) and Logistic Regression (0.8509).
* Evaluation Metric: The primary metric used for model selection was ROC-AUC (Receiver Operating Characteristic - Area Under Curve). This metric is particularly well-suited for this classification task because it effectively measures a model's ability to distinguish between the two classes (Renewed vs. Canceled) across all possible classification thresholds, providing a comprehensive assessment of its discriminatory power.
* Final Results: The selected RandomForestClassifier was evaluated on a holdout test set that was completely isolated during training and tuning. The model achieved a high level of accuracy, confirming its reliability and predictive strength.

With a verified ROC-AUC score of 0.9251 on unseen data, this model provides a highly reliable tool to support critical financial and strategic decisions in the competitive television industry.
