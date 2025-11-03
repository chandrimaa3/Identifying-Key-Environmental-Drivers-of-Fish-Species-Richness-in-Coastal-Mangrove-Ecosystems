# Identifying Key Environmental Drivers of Fish Species Richness in Coastal Mangrove Ecosystems

## Project Objective

The objective of this project is to model the relationship between key environmental variables (like water salinity, pH, temperature, and mangrove density) and the observed biodiversity (e.g., count of fish species) in coastal mangrove ecosystems. This analysis is highly relevant to MSSRF's coastal systems work.

## Project Overview

This notebook performs an analysis of the relationship between environmental variables and fish species richness using a dataset containing site locations, species counts, and environmental readings. The analysis involves data acquisition, preprocessing, exploratory data analysis (EDA), multivariate analysis using Principal Component Analysis (PCA), and Generalized Linear Model (GLM) building and selection (using Poisson and Negative Binomial regression with AIC).

## Data

The analysis in this notebook utilizes a simulated dataset for demonstration purposes. A real-world dataset with site locations, fish species counts, and environmental readings would be required for a comprehensive study.

The simulated dataset includes the following columns:

- `Site_Location`: Unique identifier for each sampling site.
- `Fish_Species_Count`: The number of fish species observed at each site (response variable).
- `Water_Salinity`: Water salinity reading at each site.
- `pH`: pH reading at each site.
- `Temperature`: Water temperature reading at each site.
- `Mangrove_Density`: A measure of mangrove density at each site.

## Analysis Steps

1.  **Data Acquisition and Loading**: A sample dataset is created and loaded into a pandas DataFrame.
2.  **Data Preprocessing and Cleaning**: The data is checked for missing values and appropriate data types. Outliers in numerical columns are handled using the Interquartile Range (IQR) method.
3.  **Exploratory Data Analysis (EDA)**: Histograms are generated to visualize the distribution of numerical variables. Scatter plots are created to examine the relationships between fish species count and environmental variables. A correlation matrix and heatmap are generated to assess the pairwise correlations between numerical variables.
4.  **Multivariate Analysis (PCA)**: Principal Component Analysis is applied to the standardized environmental variables to reduce dimensionality and identify principal components that capture most of the variance. A biplot is generated to visualize the PCA results.
5.  **Model Building (GLM)**: Generalized Linear Models (GLM), specifically Poisson and Negative Binomial regression, are built to model the relationship between the principal components and fish species richness.
6.  **Model Selection**: The Poisson and Negative Binomial models are compared using the Akaike Information Criterion (AIC) to select the most parsimonious model.
7.  **Model Interpretation and Validation**: The coefficients of the selected model are interpreted to understand the impact of the principal components on fish species richness. The significance of the coefficients is discussed based on p-values.

## Key Findings

Based on the analysis using the simulated dataset:

*   The Negative Binomial GLM was selected as the better model compared to the Poisson GLM based on a lower AIC, suggesting it's more suitable for this count data, likely due to accounting for overdispersion.
*   Neither of the two principal components included in the model were found to be statistically significant predictors of fish species count at the 5% significance level. The intercept was statistically significant.

## Limitations and Future Research

**Limitations:**

*   The analysis was conducted on a small, simulated dataset, limiting the statistical power and generalizability of the findings.
*   The simulated dataset may not fully represent the complexities of real-world coastal mangrove ecosystems.
*   The analysis was limited to the provided environmental variables; other important factors influencing fish species richness were not included.
*   The PCA and GLM approaches assume linear relationships, which may not fully capture complex ecological dynamics.
*   Formal model validation techniques were not comprehensively applied.

**Future Research Directions:**

*   Utilize larger, real-world datasets from diverse coastal mangrove ecosystems.
*   Include a wider range of environmental, biological, and anthropogenic variables.
*   Explore non-linear modeling techniques (e.g., GAMs, machine learning models).
*   Investigate interaction effects between environmental variables.
*   Incorporate spatial and temporal dynamics into the analysis.
*   Employ different dimensionality reduction methods.
*   Implement rigorous model validation techniques, including cross-validation.

## Dependencies

The following Python libraries are required to run the code in this notebook:

*   pandas
*   numpy
*   matplotlib
*   seaborn
*   sklearn
*   statsmodels

You can install these dependencies using pip:
