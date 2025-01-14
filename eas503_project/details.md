# EAS-503-Insurance Renewal Prediction Project
This project aims to predict whether an existing customer will renew their insurance plan or not. The process includes data exploration, machine learning experimentation, and deployment of the best-performing model.

[![alt text](../_static/thumb.png)](https://buffalo.app.box.com/file/1731855580208?s=wlrncijpznpb2keu3ahuifzr61jvsl5r)

**Other Important Links**:  
- **Streamlit App** [Insurance Renewal prediction](https://insuranceapp-cteu6tsf77pwn2mynpatvv.streamlit.app/)
- **DagsHub:** [Experiments](https://dagshub.com/vamsisaigarapati/insurance_renewal/experiments)  
- **DockerHub:** [Docker image](https://hub.docker.com/repository/docker/vamsisaigarapati/insurance_streamlit/general)  
- **Final Deployed Model:** Random classifier Model
- **Github:** [vamsisaigarapati](https://github.com/vamsisaigarapati/)    

---
## Steps Involved

### 1. Data Selection and Acquisition
- **Dataset**: Chose an insurance dataset containing features like age, premium, accommodation type, insurance type, etc., along with a target variable indicating renewal status.
- **Source**: Retrieved the dataset from OpenML (Dataset ID: 45064) and stored it locally.
- **Database Integration**: Leveraged a previously created normalized (3NF) database to fetch structured data using SQL queries.

### 2. Data Preparation and Exploration
- **Data Extraction**: Combined multiple tables (`FactInsurance`, `City`, `Accommodation`, `HealthIndicator`) using SQL joins to create a cohesive dataset.
- **Data Inspection**:
  - Checked for missing values and handled them appropriately.
  - Analyzed feature distributions, identifying patterns and outliers.
  - Explored relationships between features and the target variable using visualizations.
- **Feature Transformation**:
  - Encoded categorical variables.
  - Standardized numerical features where necessary.

### 3. Machine Learning Experimentation
- **Pipeline Development**: Created reusable machine learning pipelines for streamlined experimentation.
- **Experiments Conducted**:
  1. **Logistic Regression**: Baseline model to establish initial performance.
  2. **Random Forest**: Improved performance and identified as the best-performing model.
  3. **Feature Engineering**: Introduced new features based on domain knowledge to improve prediction accuracy.
  4. **Feature Selection**: Reduced dimensionality by retaining only the most impactful features.
  5. **PCA Dimensionality Reduction**: Applied Principal Component Analysis for further dimensionality reduction and noise elimination.
  6. **Feature Scaling**: Normalized features to ensure consistent input for algorithms sensitive to feature magnitude.
  7. **Polynomial Features**: Augmented feature space by generating interaction terms and polynomial terms.

- **Metrics Tracking**: Logged experiments and evaluated models using MLflow integrated with DagsHub.
- **Model Selection**: Random Forest was identified as the best model based on metrics like accuracy, precision, recall, and F1 score.

### 4. Model Deployment
- **Hosting**:
  - Packaged the Random Forest pipeline into a FastAPI application.
  - Deployed the API on a cloud platform (DigitalOcean) to serve predictions.
- **User Interface**:
  - Built a Streamlit web application to provide an interactive interface for users.
  - Integrated the app with the deployed FastAPI endpoint to facilitate real-time predictions.

### Tools and Technologies Used
- **Data Handling**: Python (pandas, SQLite3), SQL
- **Modeling and Logging**: scikit-learn, MLflow, DagsHub
- **Deployment**: FastAPI, Streamlit, DigitalOcean

### Project Outcomes
- Successfully identified a robust machine learning pipeline for predicting insurance plan renewals.
- Deployed a scalable API and an intuitive web application for real-time predictions.

---

### Files and Artifacts
- **Notebook**: Contains EDA, feature engineering, and model experimentation steps.
- **API**: FastAPI implementation for serving predictions.
- **Web App**: Streamlit code for user interaction.
- **Database**: SQLite database for fetching and preparing data.
