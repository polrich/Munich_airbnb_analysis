# Find your best travel specifications for munich

When you are planning to visit a major city, such as munich, finding a suitable and affordable accommodation is often tedius. But what are the main affects that influence prices? Is it the particular part of the city, the distance to the clostest underground station, the time of the year, the simultaneous occurance of trading fairs or Oktoberfest, ratings and reviews of an accommodation or simply the amenities provided by the host? Is it possible to save some money without losing comfort?

I will try to answer these questions by analysing the [AirBnB](https://www.kaggle.com/datasets/chriskue/munich-airbnb-data) data available for munich from [Kaggle](https://www.kaggle.com/). 

## Files in the repository and their usage
I have downloaded three files from Kaggle into the repo:
- calendar.csv: calender data for listings, like dates and prices 
- listings.csv: summary on listings, like location, host infos, fees, amenities
- reviews.csv: summy on reviews for the listings

If you want to re-run the analysis itself, just deploy Munich_Airbnb_analysis.ipynb in a jupyter notebook.

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

## Short summary of the analysis
We tried to understand on basis of AirBnB data for munich, which features have a high influence on the accommodation prices for this city. Therefore we formulated 5 questions:

How large is the influence on munich airbnb accommodation prices for
1. Neighbourhood of the city
2. Time of the year
3. Ratings and reviews of the accommodation
4. Size, number of rooms and beds etc
5. Provided amenities

We can fairly clearly answer most of this questions.

1. The neighbourhood has a very high influence on the price. We identified top price regions like `Altstadt-Lehel` and `Ludwigsvorstadt-Isarvorstadt`, whereas there are also some rather cheap ones.
2. The time of the year has also a high impact on prices. Cheapest would be february. If you want some warm weather, it would be adviseable to visit in july. However, if you want to attend Oktoberfest, you will have to pay highest prices for the time of september.
3. The ratings and reviews have only small influence on the price. Whereas the score does not have a high influence on the pricing, it has an influence on the number of bookings. If a score is >70, the number of bookings increases exponentially.
4. Size could not be used directly, and most other related variables can be condensed to number of accommodates. The price per accommodation rises linearly from 1-10, then there is a peak due to highly biased data for a certain region of munich with 11 accomodates. Neglecting this, the trend is linearly rising from 1-12 accomodates. For more than >12 people the price seems to get lower.
5. As we can see, there are unfortunately lots of amenities. However, there are some trends.
E.g. and `indoor fireplace` or `waterfront` has a very positive effect on prices, whereas e.g. `pets live on this property` has a negative. In the end there are some amenities that should not be reviewed for a report.
