# python-api-challenge

# Python API Bootcamp Assignment - What's the Weather Like?

## Background

Whether financial, political, or social -- data's true power rests in its ability to answer questions definitively. So, let's take what you've learned about Python requests, APIs, and JSON traversals to answer a fundamental question: "What's the weather like as we approach the equator?"

Now, we know what you may be thinking: _"Duh. It gets hotter ..."_

But, if pressed, how would you **prove** it?

### Setup

1. Create a new repository for this project called `python-api-challenge`.

2. Clone the new repository to my computer.

3. Inside my local Git repository, create a directory for both of the Python challenges. Use a folder name that corresponds to the challenges, such as **WeatherPy**.

4. Inside the folder you just created, add new files called `WeatherPy.ipynb` and `VacationPy.ipynb`. These will be the main scripts to run for each analysis.

5. Push the above changes to GitHub.


### Adding a .gitignore File

Before we adding files to GitHub, add `api_keys.py` to the `.gitignore` file. By using the following instructions:

1. Open your `python-api-challenge` GitHub folder in VS Code.

2. Open the `.gitignore` file, and on the first line, type the following code:

```python
# Adding config.py file.
api_keys.py
```

3. In the command line, type `git status` and press Enter. The output should indicate that the `.gitignore` file has been modified and the `WeatherPy.ipynb` file is untracked.

4. Use `git add`, `git commit`, and `git push` to commit the modifications to `.gitignore` and the `WeatherPy.ipynb` file to GitHub.

On GitHub, the only new file you should find is the `WeatherPy.ipynb` file.

## Part 1: WeatherPy

In this section, create a Python script to visualize the weather of 500+ cities of varying distance from the equator. To do so, use a [simple Python library](https://pypi.python.org/pypi/citipy), the [OpenWeatherMap API](https://openweathermap.org/api), and problem-solving skills to create a representative model of weather across cities.

The first requirement was to create a series of scatter plots to showcase the following relationships:

* Temperature (F) vs. Latitude
* Humidity (%) vs. Latitude
* Cloudiness (%) vs. Latitude
* Wind Speed (mph) vs. Latitude

After each plot, add a sentence or two explaining what the code is analyzing.

The second requirement was to compute the linear regression for each relationship. This time, separate the plots into Northern Hemisphere (greater than or equal to 0 degrees latitude) and Southern Hemisphere (less than 0 degrees latitude):

* Northern Hemisphere - Temperature (F) vs. Latitude
* Southern Hemisphere - Temperature (F) vs. Latitude
* Northern Hemisphere - Humidity (%) vs. Latitude
* Southern Hemisphere - Humidity (%) vs. Latitude
* Northern Hemisphere - Cloudiness (%) vs. Latitude
* Southern Hemisphere - Cloudiness (%) vs. Latitude
* Northern Hemisphere - Wind Speed (mph) vs. Latitude
* Southern Hemisphere - Wind Speed (mph) vs. Latitude

After each pair of plots, explain what the linear regression is modeling. For example, describe any relationships that I noticed and any other findings.

Final notebook must:

* Randomly select **at least** 500 unique (non-repeated) cities based on latitude and longitude.
* Perform a weather check on each of the cities using a series of successive API calls.
* Include a print log of each city as it's being processed, with the city number and city name.
* Save a CSV of all retrieved data and a PNG image for each scatter plot.

### Part 2: VacationPy

Now, use skills working with weather data to plan future vacations. Use Jupyter-gmaps and the Google Places API for this part of the assignment.

* **Note:** Remember that any API usage beyond the $200 credit will be charged to your personal account. Set quotas and limits to daily requests to be sure of unexpected charges. Check out [Google Maps Platform Billing](https://developers.google.com/maps/billing/gmp-billing#monitor-and-restrict-consumption) and [Manage your cost of use](https://developers.google.com/maps/documentation/javascript/usage-and-billing#set-caps) for more information.

* **Note:** Having trouble displaying the maps? Run `jupyter nbextension enable --py gmaps` in terminal and retry.

To complete this part of the assignment, I had to do the following:

* Create a heat map that displays the humidity for every city from Part 1

* Narrow down the DataFrame to find your ideal weather condition. For example:

  * A max temperature lower than 80 degrees but higher than 70.

  * Wind speed less than 10 mph.

  * Zero cloudiness.

  * Drop any rows that don't satisfy all three conditions. You want to be sure the weather is ideal.

* Use Google Places API to find the first hotel for each city located within 5,000 meters of my coordinates.

* Plot the hotels on top of the humidity heatmap, with each pin containing the **Hotel Name**, **City**, and **Country**
