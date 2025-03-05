# Project-AirQuality-Analysis
This repository presents a comprehensive study on air pollution levels in the Monterrey Metropolitan Area (MMA), addressing everything from data collection and imputation of missing values, to the construction of multiple linear regression models and principal component analysis (PCA) to reduce multicollinearity, in addition to K-Means segmentation techniques. Throughout the project, interactive visualizations, detailed statistical evaluations, and methodological considerations are included for the selection of the best approaches at each stage of the Data Science process.
Project Overview

Context and Objective
Data related to air quality in Monterrey are analyzed, with an emphasis on the PM2.5 pollutant, known for its adverse effects on health.
The objective is to understand which meteorological factors and pollutants (NO, NO2, NOX, etc.) best explain the variation of fine particles in the air, and to predict their future levels to support environmental decision making.

Imputation of Missing Data
Multiple methods (linear interpolation, polynomial, spline, forward/backward fill, moving average, exponential smoothing, and preliminary regression) are tested to fill gaps in the PM2.5 series.
Prediction errors (MSE, RMSE) are compared and a hypothesis test (F-test) is performed to select the most reliable method, balancing noise reduction and preservation of the original trend.

Exploratory Analysis and Visualizations
Includes boxplots, interactive time series (Plotly) and heat maps (correlation matrices) to investigate data dispersion, presence of outliers and relationships between variables.
This analysis helps detect multicollinearity problems and justify the use of PCA in later stages.

Predictive Modeling
Multiple Linear Regression (without PCA): It is trained with a set of predictors (pollutants and meteorological factors), evaluating their performance (adjusted R², MSE, cross-validation with TimeSeriesSplit).
Multiple Linear Regression (with PCA): For strongly correlated variables (NO, NO2, NOX), PCA is applied in order to reduce dimensionality and attenuate multicollinearity. Results (e.g., adjusted R², silhouette coefficients, etc.) are compared against the initial model.

Cluster Analysis (K-Means)
Unsupervised segmentation methods (K-Means) are applied to group observations based on pollutant concentrations.
Different K values ​​(2, 3, etc.) are examined and the silhouette coefficient is calculated to measure the internal consistency of the clusters.
Clusters are visualized in 3D (using PCA) to detect “High vs. Low Pollution” groups.

Main Results
The best imputation method (according to the MSE and the F test) was the preliminary regression, although multiplicative exponential smoothing and linear interpolation were considered as plausible alternatives depending on the series.
The regression model without PCA obtained an acceptable adjusted R² in training, but showed some overfitting (negative adjusted R² in tests), evidencing the need for approaches that reduce collinearity.
By incorporating PCA, the training adjusted R² decreased, but in some cases less overfitting is observed. The use of PCA helped to isolate the strong correlation between NO, NO2 and NOX.
With K-Means, a K = 3 showed better silhouette coefficient (∼0.37), suggesting clearer separations between periods/zones of higher and lower pollution.

