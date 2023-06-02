# Find your best travel specifications for munich

When you are planning to visit a major city, such as munich, finding a suitable and affordable accommodation is often tedius. But what are the main affects that influence prices? Is it the particular part of the city, the distance to the clostest underground station, the time of the year, the simultaneous occurance of trading fairs or Oktoberfest, ratings and reviews of an accommodation or simply the amenities provided by the host? Is it possible to save some money without losing comfort?

I will try to answer these questions by analysing the [AirBnB](https://www.kaggle.com/datasets/chriskue/munich-airbnb-data) data available for munich from [Kaggle](https://www.kaggle.com/). 

## Files in the repository and their usage
I have downloaded three files from Kaggle into the repo:
- calendar.csv: calender data for listings, like dates and prices 
- listings.csv: summary on listings, like location, host infos, fees, amenities
- reviews.csv: summy on reviews for the listings

If you want to re-run the analysis itself, just deploy Munich_Airbnb_analysis.ipynb in a jupyter notebook.

In addition you will find a few .jpgs. They were saved during the deployment of the notebook above.

## Necessary libraries
You will need the following (standard) libraries for python:
```
import numpy as np
import pandas as pd

import matplotlib.pyplot as plt
%matplotlib inline
import seaborn as sns

from sklearn.linear_model import LinearRegression
from sklearn.model_selection import train_test_split
from sklearn.metrics import r2_score, mean_squared_error

import warnings
warnings.simplefilter(action='ignore', category=pd.errors.PerformanceWarning)
warnings.simplefilter(action='ignore', category=FutureWarning)
```
