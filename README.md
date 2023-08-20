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
