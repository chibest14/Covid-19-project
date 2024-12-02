# Covid-19-project
# Analysis And Predictive Modelling for COVID-19 in Public Health

Summary of Findings

*Data Quality:* The dataset was generally clean, with no duplicate entries. However, some negative values were found in the 'Active', 'New deaths', and 'New recovered' columns, which were addressed using median imputation.
*Outliers and Distribution:* Several numerical features, including 'Confirmed', 'Deaths', 'Recovered', 'Active', 'New cases', 'New deaths', and 'New recovered' exhibited outliers and skewed distributions. Log transformation was applied to these features to address the skewness and improve model performance.
*Trends:* The analysis revealed an overall upward trend in COVID-19 cases, deaths, and recoveries over time. The Americas and Europe showed the highest cumulative confirmed cases.
*Correlation:* A strong positive correlation was observed between confirmed cases, deaths, and recovered cases. This correlation is expected as these metrics are inherently linked.
*Model Performance:* The ARIMA(1, 1, 1) model performed well in predicting log-transformed new cases. The predicted values closely followed the actual values, indicating the model's ability to capture underlying trends.
Steps Taken

*Data Loading and Preprocessing:* The COVID-19 dataset was loaded into a Pandas DataFrame, and initial data quality checks were performed.
*Handling Missing and Negative Values:* Negative values were replaced with the median, and missing values (introduced during feature engineering) were filled with 0.
*Exploratory Data Analysis (EDA):* Visualizations such as box plots, histograms, and bar charts were used to understand the distribution, trends, and relationships between variables.
*Feature Engineering:* New features, including 'Daily Growth Rate', 'New Cases MA7', 'New Deaths MA7', and 'New Recoveries MA7', enhanced model performance and revealed additional insights.
*Log Transformation:* Log transformation was applied to selected numerical features to address skewness and outliers.
*Correlation Analysis:* A correlation matrix was generated to examine the relationships between variables.
*Model Selection and Training:* An ARIMA(1, 1, 1) model was selected based on the data characteristics and trained on the log-transformed 'New cases' data.
*Model Evaluation:* The model's performance was evaluated using RMSE and visualized by comparing predicted values with actual values.
# ARIMA Model Explanation

*ARIMA (Autoregressive Integrated Moving Average):* A statistical model used for time series analysis and forecasting.
Components:
*AR (Autoregressive):* Uses past values of the series to predict future values.
*I (Integrated):* Represents the differencing applied to make the time series stationary (constant mean and variance).
*MA (Moving Average):* Uses past forecast errors to improve future predictions.
*ARIMA(1, 1, 1):* This specific model uses one autoregressive term, one order of differencing, and one moving average term.
What the Model is Doing

*Capturing Trends:* The ARIMA model identifies and captures underlying trends and patterns in the time series data (log-transformed new cases).
*Forecasting:* It uses this information to make predictions about future values, providing insights into the potential trajectory of COVID-19 cases.
*Adjusting for Stationarity:* The differencing component (I = 1) helps to make the time series stationary, which is a requirement for many time series models.
*Accounting for Errors:* The moving average component (MA = 1) incorporates past forecast errors to improve the accuracy of future predictions.
