<b>Problem Statement</b>

A bike-sharing system is a service in which bikes are made available for shared use to individuals on a short term basis for a price or free. Many bike share systems allow people to borrow a bike from a "dock" which is usually computer-controlled wherein the user enters the payment information, and the system unlocks it. This bike can then be returned to another dock belonging to the same system.

A US bike-sharing provider BoomBikes has recently suffered considerable dips in their revenues due to the ongoing Corona pandemic. The company is finding it very difficult to sustain in the current market scenario. So, it has decided to come up with a mindful business plan to be able to accelerate its revenue as soon as the ongoing lockdown comes to an end, and the economy restores to a healthy state.

In such an attempt, BoomBikes aspires to understand the demand for shared bikes among the people after this ongoing quarantine situation ends across the nation due to Covid-19. They have planned this to prepare themselves to cater to the people's needs once the situation gets better all around and stand out from other service providers and make huge profits.

They have contracted a consulting company to understand the factors on which the demand for these shared bikes depends. Specifically, they want to understand the factors affecting the demand for these shared bikes in the American market. The company wants to know:

Which variables are significant in predicting the demand for shared bikes.
How well those variables describe the bike demands
Based on various meteorological surveys and people's styles, the service provider firm has gathered a large dataset on daily bike demands across the American market based on some factors.


<b>Business Goal:</b>

You are required to model the demand for shared bikes with the available independent variables. It will be used by the management to understand how exactly the demands vary with different features. They can accordingly manipulate the business strategy to meet the demand levels and meet the customer's expectations. Further, the model will be a good way for management to understand the demand dynamics of a new market.

<b>Approach to Problem Solving</b>

There are 9 steps that has been done in order to arrive at model, to validate and verify. A brief explanation of the various steps are as below:

<b>1. Reading and understanding the data set</b>

The data set was analysed and basic data checks like the columns, count of rows, data types etc were done to understand the data in depth.
The data along with given characteristics was analysed for null, redundant and unnecessary columns and those were removed from the dataset.

Summary of the Dataset characteristics

day.csv have the following fields:

	- instant: record index
	- dteday : date
	- season : season (1:spring, 2:summer, 3:fall, 4:winter)
	- yr : year (0: 2018, 1:2019)
	- mnth : month ( 1 to 12)
	- holiday : weather day is a holiday or not (extracted from http://dchr.dc.gov/page/holiday-schedule)
	- weekday : day of the week
	- workingday : if day is neither weekend nor holiday is 1, otherwise is 0.
	+ weathersit :
		- 1: Clear, Few clouds, Partly cloudy, Partly cloudy
		- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist
		- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds
		- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog
	- temp : temperature in Celsius
	- atemp: feeling temperature in Celsius
	- hum: humidity
	- windspeed: wind speed
	- casual: count of casual users
	- registered: count of registered users
	- cnt: count of total rental bikes including both casual and registered

<b>2. Visualizing the data set</b>

The data set was visualised using scatter and box plots for numerical and categorical values. The outliers data was analysed.
We can also check for any patterns in the charts . Coefficients between all variables are plotted to verify if any variables are closely related to any other.

<b>Step 3: Data Preparation</b>

We had to change few columns that were categorical but had numerical values like weather sit, season etc.
We modified these columns values into labels and also created them as dummy variables. After creating the dummy variables,
 we deleted the previous ones.

<b>Step 4: Splitting the Data into Training and Testing Sets</b>

Using sklearn.model_selection library, we split the datasets into training and test data sets in the ratio of 70-30 respectively .
The feature scaling is also done as part of the splitting data set.

<b>Step 5: Building a linear model</b>

After cleaning and creating the datasets, the model building is done as part of this step using the stats model.
We train the model, verify the R squared and VIF values to see if the model has the best fit. If not, we remove the insignificant variables and then retrain the model.
The process is repeated multiple times till we arrive at the best fit model.

<b>Step 6: Residual Analysis of the train data</b>

Once the data is trained, we analyse the residuals and validate if it is normally distributed. Since for a linear regression, it is crucial to have the residuals normally distributed.

<b>Step 7: Making Predictions Using the Final Model</b>

Now that we have fitted the model and checked the normality of error terms, it's time to go ahead and make predictions using best fit model.

<b>Step 8: Evaluating the Model</b>

The test and predicted values using the model is plotted to check how the model has worked with the test data. We also evaluate the R-squared for train data and
R-squared for test data if they are similar.
