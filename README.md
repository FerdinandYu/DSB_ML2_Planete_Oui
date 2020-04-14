# Planete Oui Data Challenge

https://challengedata.ens.fr/participants/challenges/29/

## Challenge goals
The goal is to train an algorithm to replace many monitoring systems which are too intrusive and too expensive. This challenge is known as NILM (Nonintrusive load monitoring) or NIALM (Nonintrusive appliance load monitoring). The aim of the challenge is to find the part of electric consumption in one household dedicated to 4 appliances (washing machine, fridge_freezer, TV, kettle). There are no time constraints. The past and the future are known.

## Data description
The first line of the input contains the header, the columns are separated by ',', and decimals by decimal point. The columns are:

* the “time_step”: date measured each minute (format yyyy-MM-ddTHH :mm :ss.Z)
* the “consumption”: household consumption (W) measured each minute
* the “visibility”: distance at which it is possible to clearly distinguish an object (km) measured once per hour
* the “temperature”: temperature (°C) measured once per hour
* the “humidity”: presence of water in the air (%) measured once per hour
* the “humidex”: index used to integrate the combined effects of heat and humidity measured once per hour
* the “windchill”: an index that expresses the subjective feeling of cold or heat as a function of measured temperature, wind and humidity (°C) measured once per hour
* the “wind”: wind speed (km/h) measured once per hour
* the “pressure”: applied perpendicular to the surface of an object per unit area (Pa) measured once per hour

The first line of the output contains the header, the columns are separated by ',', and decimals by decimal point. The columns are:

* the “time_step”: date measured each minute (format yyyy-MM-ddTHH :mm :ss.Z)
* the “washing_machine”: washing machine power (W) measured each minute
* the “fridge_freezer”: fridge freezer power (W) measured each minute
* the “TV”: TV power (W) measured each minute
* the “kettle”: kettle power (W) measured each minute

The train set contains 417 599 values with 10 231 missing values (2,44%) for “consumption”, “washing_machine”, “fridge_freezer”, “TV”, “kettle” and the test set contains 226 081 values with 24 719 missing values (10,93%).

## Benchmark description
The benchmark is on 4 univariate linear regressions (one per appliance). The inputs are consumption of the household, the day of the week (7 booleans), the weekend (1 boolean), and the circular hour of the day (sine and cosine).

L(y_hat, y) = 47.64W
