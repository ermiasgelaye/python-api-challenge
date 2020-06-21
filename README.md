# Python API Challenge - What's the Weather Like?

## Background

This project has two parts one used an API requests, and Python script to visualize the weather date of 500+ cities across the world of varying distance from the equator, and sourced under [**WeatherPy folder**](WeatherPy/). To accomplish th, I utilized a [**simple Python library**](https://pypi.python.org/pypi/citipy), the [**OpenWeatherMap API**](https://openweathermap.org/api), and created a representative model of weather across world cities.The cities dataset found in [**output_data folder**](WeatherPy/output_data/cities.csv) which includes the following columns `City_ID`,`City`,`Cloudines`,`Country`,`Date`,`Humidity`,`Lat`,`Lng`,`Max`,`Temp`,`Wind Speed`. The data analyzed, and displayed on [jupyter notebook](WeatherPy/WeatherPy.ipynb) , and the results are exported in csv format [**city_weather_data.csv**](WeatherPy/output_data/city_weather_data.csv), and the regression plots [**output_data folder**](WeatherPy/output_data/).

The other project [**VacationPy**](VacationPy/) is used the output data from the previous task [**city_weather_data.csv**](WeatherPy/output_data/city_weather_data.csv) to plan for future vacations. For this part of analysis the a jupyter-gmaps, and the Google Places were used, and the results are displayed[**jupyter notebook**](VacationPy/VacationPy.ipynb). Basically, the analysis covers humidity heatmap in the cities that sourced from the weather data, and plot the hotels on top of the humidity heatmap. You can look the images in the out put folder for bott [**the heatmap**](VacationPy/output_data/Heatmap.png) and [**the hotel heatmap**](VacationPy/output_data/hotel.png,)images.

## <a name="api_keys"></a> API Keys


To run localy the python files for both [WeatherPy](WeatherPy/WeatherPy.ipynb),and [jupyter notebook](VacationPyy/VacationPy.ipynb) projects you need to obtain API keys. For part one, you will need to obtain an API key for the OpenWeatherMap API, which can be obtained [here](https://home.openweathermap.org/api_keys). After you have the OpenWeatherMap API key, in the **WeatherPy** folder, [**config.py**](WeatherPy/api_keys.py) file add the API key there it looks as follows:

```bash
weather_api_key="API_KEY_HERE"

```
For part two, you wll need to obtain a Google API key from the Google Cloud Platform at <https://cloud.google.com> and enable the **Places API**. After you have the Google API key,in the **VacationPy** folder, [**config.py**](VacationPy/api_keys.py) file add the API key there it looks as follows:

```bash
g_key="API_KEY_HERE"
```

## Part I - WeatherPy
![Equator](Images/equatorsign.png)

In this example, you'll be creating a Python script to visualize the weather of 500+ cities across the world of varying distance from the equator. To accomplish this, you'll be utilizing a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and a little common sense to create a representative model of weather across world cities.

Your first requirement is to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot add a sentence or too explaining what the code is and analyzing.

Your second requirement is to run linear regression on each relationship, only this time separating them into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots explain what the linear regression is modeling such as any relationships you notice and any other analysis you may have.

**Optional** You will be creating multiple linear regression plots. To optimize your code, write a function that creates the linear regression plots.

Your final notebook must:

* Randomly select **at least** 500 unique (non-repeat) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

### Part II - VacationPy

Now let's use your skills in working with weather data to plan future vacations. Use jupyter-gmaps and the Google Places API for this part of the assignment.

* **Note:** if you having trouble displaying the maps try running `jupyter nbextension enable --py gmaps` in your environment and retry.

* Create a heat map that displays the humidity for every city from the part I of the homework.

  ![heatmap](Images/heatmap.png)

* Narrow down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drop any rows that don't contain all three conditions. You want to be sure the weather is ideal.

  * **Note:** Feel free to adjust to your specifications but be sure to limit the number of rows returned by your API requests to a reasonable number.

* Using Google Places API to find the first hotel for each city located within 5000 meters of your coordinates.

* Plot the hotels on top of the humidity heatmap with each pin containing the **Hotel Name**, **City**, and **Country**.

  ![hotel map](Images/hotel_map.png)




### Copyright

Trilogy Education Services © 2019. All Rights Reserved.
