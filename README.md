# Predicting the number of bike rentals in a day

<p>The dataset for this project was obtained from https://archive.ics.uci.edu/ml/datasets/bike+sharing+dataset. The number of bikes rented out per day in the years 2011 and 2012 in a city on the East coast of U.S., along with features describing the day e.g. temperature, day of the week, humidity, is contained in the file named 'day.csv'</p>

<p>The full list of attributes:
  <ul>
    <li>instant: record index </li>
<li>dteday : date </li>
<li>season : season (1:winter, 2:spring, 3:summer, 4:fall) </li>
<li>yr : year (0: 2011, 1:2012) </li>
<li>mnth : month ( 1 to 12) </li>
<li>holiday : weather day is holiday or not </li>
<li>weekday : day of the week </li>
<li>workingday : if day is neither weekend nor holiday is 1, otherwise is 0. </li>
<li>weathersit : 
- 1: Clear, Few clouds, Partly cloudy, Partly cloudy 
- 2: Mist + Cloudy, Mist + Broken clouds, Mist + Few clouds, Mist 
- 3: Light Snow, Light Rain + Thunderstorm + Scattered clouds, Light Rain + Scattered clouds 
- 4: Heavy Rain + Ice Pallets + Thunderstorm + Mist, Snow + Fog 
<li>temp : Normalized temperature in Celsius. The values are derived via (t-t_min)/(t_max-t_min), t_min=-8, t_max=+39 (only in hourly scale) </li>
<li>atemp: Normalized feeling temperature in Celsius. The values are derived via (t-t_min)/(t_max-t_min), t_min=-16, t_max=+50 (only in hourly scale) </li>
<li>hum: Normalized humidity. The values are divided to 100 (max) </li>
<li>windspeed: Normalized wind speed. The values are divided to 67 (max) </li>
<li>casual: count of casual users </li>
<li>registered: count of registered users </li>
<li>cnt: count of total rental bikes including both casual and registered</li>
</ul>
</p>

<p>There were 4 outliers found on the dates: 29th October in both 2011 and 2012, 30th Ocober in 2012, and 27th August 2011. These dates had far fewer bike rentals than expected for these months. Through a quick google search, it can be found that these dates correspond to hurricane Irene in August 2011, hurricane Rine in October 2011 and hurrican Sandy in October 2012. These data points were removed from the dataset.</p>

<p>Random forest and XGBoost models performed similarily with a root mean square error of around 1200 bikes. This is a relatively high error, however, given that the mean is around 4500 it suggests that the predictive model is more likely only useful when higher bike rental numbers are expected, i.e. above 2000. This model can be used by the bike rental company to anticipate high number of bike rentals at least a day ahead, because the features in the model can be found easily. It is evident, though, that several more years of data are needed to create a more reliable model as the number of instances in this dataset is only 731. It is also possible that a more reliable model can be built using the hourly bike rental data, rather than the daily bike rental data. </p>
