Problem statement:
Now a days the demand of bike has increased, for that many big cities offer rental bike to increase mobility.
Providing the city with a consistent supply of rental bikes is a major issue that must be addressed. It is possible to maintain a consistent supply of rental bikes by accurately estimating demand for rental bikes.
This is the business issue that we will attempt to solve in this analysis.

What did we get from the dataset?
There are 8760 observations and 14 features.
In a day there are 24 hours and we have 365 days a year so 365 multiplied by 24 = 8760 which represents the number of line in dataset.
There are no null values.
Thre are no duplicate values.
Date has object type data type need to change into datetime data type.


Feature description
Breakdown of the features

Date: The date of the day for the 365 days , it is object type we need to convert into Datetime format.

Rented Bike Count: Number of rented bike per hour which is our dependent variable and we need predict that.

Hour: The hour of the day from 0 to 23 , type: int,we need convert category datatype.

Temperature(°C):Temperature in celcius , type:int.

Humidity(%) : Humidity is in percentage , type: int.

Wind speed(m/s) : Speed of the wind in m/s, type:Float.

Visibilty(10m): Visibility in m ,type:int.

Dew point temperature: Temperature at the begining of the day, type:float

Solar Radiation (MJ/m2): Sun contribution, type: float

Rainfall(mm): Amount of raining in mm, type:Float

Snowfall(cm): Amount of snowing in cm, type: float

Seasons: Seasons of the year, type:Str

Holiday: If the day holiday or not, type: str

Functioning day: if the day is Functioning or not, type: str.


I converted the date column into year, day, month.
I dropped year, day, date column because i don't see any analysis can be drawn from it ,to make insightful i extracted weekdays and weekends from the day column .



As we can see the dependent variable is postively right skewed.
The ideal dependent variable should be normally distributed.
To achieve normal distribution we can use log , sqrt etc to transform.



From visualizing the continous independent variable we can that:

Normarly distributed variables: Temprature , Humidity
Positively skewed variables: Wind speed , rainfall, snowfall,solar radiation
Negatively skewed variables: Visibility




From the visualization we can infer that:

In winters the overall demand for rented bikes is comparitively lower than that of other seasons.
On a non functioning day, no bikes are rented.
The demand for rented bikes throughout the day on holidays and weekends follow a different pattern than other days. On regular days, the demand for the bikes is higher during rush hours. On holidays or weekends, the demand is comparitively lower in the mornings, and is higher in the afternoons




Summary and Conclusion
We trained 5 unique Machine Learning models using the training dataset, and the its respective performance was improved through hyperparameter tuning.
We initially started with the Linear regression model, mainly because it is Linear regression models are straightforward to interpret. we can easily understand the effect of each feature on the target variable by examining the coefficients.
Once we were successfully able to fit a Linear regression, it was necessary to improve the prediction accuracy, and reduce errors in the predictions.
Then we used Ridge regression with hyparameter tunning which helps mitigate issues like multicollinearity and overfitting.
Then we use Decision tree because of low training time.
Once we were successfully able to fit a decision tree, it was necessary to improve the prediction accuracy, and reduce errors in the predictions.
To achieve this, we fit a random forest model on the training data, and the final predictions showed less errors compared to that of decision tree model.
To further improve the predictions of the model, we fit 2 boosting models namely; Gradient boosting machine (GBM) and Extreme gradient boost (XG Boost). The predictions obtained from these models showed errors in the same range, but the errors were lower than that of decision tree model.
The XG Boost model has the lowest RMSE, and the highest R2 score.

If we want model with best accuracy then XG boost is best because it has low bias and low variance
higher the model complexity, lower is the model explainability. Hence if the predictions must be explained to stakeholers, then XG Boost is not an ideal choice. In this case decision tree can be used, since they are easier to explain.
