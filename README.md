# Linear Regression Data Science Project on Canadian Rents
## Technology: Python, Pandas, NumPy, Seaborn, Matplotlib, Ridge, Scikit-Learn, Lasso, TensorFlow
## Data Science Method: Data Manipulation, Visualization, Linear Regression, Deep Learning
## Case Descriptions
The purpose of this project is to gain insights and learn patterns between the features and the pricing of rents in Canada. I will also build three different regression models to predict the rents in Canada given different features.
## Datasets Description
It has 18 columns and 25771 rows. Not all the features are in the right data type. Some data type needs to be converted to numerical from strings. There are null values in multiple columns.
The features are rentfaster_id (int64), city (object), province (object), address (object), latitude (float64), longitude (float64), lease_term (object), type(object), price(float), beds (object), baths(object), sq_feet (object), link (object), furnishing (object), availability_date (object), smoking (object), cats (object), dogs (object).
Data Cleaning
Drop irrelevant features such as rentfaster_id, address, link, availability_date. And drop all the rows with null values. Convert cats, dogs, baths, sq_feet to numeric values. Drop rows where price is 0 or sq_feet is 0 since they don’t quite make sense. After the cleaning up, there are 18786 rows and 14 columns left comparing to 18 columns and 25771 rows before.
## EDA Findings
1.	Most of the properties are in latitude of 51 and longitude of -115 and -80. 
2.	Most prices are under 5000 dollars per month.
3.	Most apartments have one or two bathrooms.  
4.	Most of the apartments are under 3000 feet.
5.	Most of the apartments allow pets 
6.	The most expensive properties above 5000$ lie in Calgary, Toronto, Montreal, Vancouver and Halifax. The most expensive properties above 5000$ per month are in Alberta, Ontario, and BC. 
 
7.	The apartments with over 2000 sq feet are in Calgary and Edmonton. Most of large apartments are located in Alberta. The cities with most rents price over 5000$ are Calgary, Toronto, Montreal, Vancouver, and Halifax. The provinces with the most rents over 5000 are Alberta, Ontario, and BC. 

   
## Correlation Analysis
1.	The larger the area is, the more bathrooms it has, the more expensive the rent is.
2.	The lower the longitude, or the more south the property is located, the more expensive the rent is. 
 kk


## Category Count Analysis
1.	The province of Alberta, Ontario, and Quebec have the most rent available.
2.	Most of rents available are long term.
3.	Most types of rents available are apartments, condo units, and townhouses.
4.	Most of rents came in 2, 3, and 1 bed. The fewer the beds, the more it is available.
5.	Majority of rents are unfurnished. And Most of rents are not allowed to smoke.
 


## Average Price Category Analysis
1.	Nova Scotia and BC have the highest average rent.
2.	The priciest rents are the short-term rent such as 6 months or under 6 months.
3.	The most expensive types are vacation homes and acreage.
4.	Smoking allowed rents are lower than smoking not allowed.
 
 

## Feature Engineering
1.	Drop city feature.
2.	Apply one hot encoding on all the category features.
3.	Scale all the features.

## Machine Learning Models – Lasso
1.	Model Tuning: alphas set as 10**np.linspace(-3,3,200). The best alpha was 0.001
2.	Train the model with Lasso CV.
3.	The training r2 Score is 0.6172, and the testing r2 Score is 0.5977.
4.	The training adjusted r2 Score is 0.6160, and the testing adjusted r2 Score is 0.5929.
5.	The testing Mean Squared Error is 282014.42, and the testing Root Mean Squared Error is 531.05, and the testing Mean Absolute Error is 353.16. 
6.	Model is not underfit, but the accuracy rate was not very high. 
7.	In the chart below, the predicted values and observed values scatter widely along the diagonal line. 
 

## Machine Learning Models – Ridge
1.	Model Tuning: alphas set as 0.001, 0.01, 0.1, 1 ,10, 100 The best alpha was 0.001
2.	Train the model with Ridge CV.
3.	The training r2 Score is 0.6172, and the testing r2 Score is 0.5975.
4.	The training adjusted r2 Score is 0.6161, and the testing adjusted r2 Score is 0.5927.
5.	The testing Mean Squared Error is 282181.49, and the testing Root Mean Squared Error is 531.207, and the testing Mean Absolute Error is 353.35. 
6.	The ridge metrics are very close to those with lasso. Model is not underfit, but the accuracy rate was not very high. 
7.	In the chart below, the predicted values and observed values scatter widely along the diagonal line. 
 

## Deep Learning Models
1.	Set up 3 hidden layers with 100 neurons for each hidden layers and drop out rate of 20% for the first layer.
2.	Set 100 epochs, batch size of 50 and validation split as 0.2.
8.	The model performs better than the previous two. The predicted values and observed values scatter slightly widely along the diagonal line. 
3.	Model Metrics. he training r2 Score is 0.7479, and the testing r2 Score is 0.7039.
4.	The training adjusted r2 Score is 0.7471, and the testing adjusted r2 Score is 0.7003. it’s not overfit and comparingly accurate.
5.	The testing Mean Squared Error is 207598.42, and the testing Root Mean Squared Error is 455.63, and the testing Mean Absolute Error is 306.55. 
 
## Conclusions
1.	Insights. Alberta, Ontario, BC, Nova Scotia have the highest housing price. Metropolitan cities such as Calgary, Edmonton, Toronto, Vancouver, and Montreal have high rents. Calgary has the most expensive rents.
2.	Short term leases cost more than long term leases. 
3.	Rents with more living rooms and baths rooms are more expensive. 
4.	Deep Learning model has the highest training accuracy of 74% and testing accuracy of 70%. It’s not overfit. 
