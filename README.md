# Surfs Up Analysis

## Overview

This projects aims to analyse temperature data from Oahu island in order to evaluate the feasability of a business, which may be susceptible to seasonality. This analysis used jupyter notebook, pandas, sqlalchemy, and sqlite.

## Results

- Data was collected and summarized by the months of June and December in several years.
- June summary shows an average temperture of 74.944118, having a minimum temperature of 64 and a maximum of 85.
- For Decermber data, the average is 71.041529, with a minimum of 56 and a maximum of 83.
- Both summaries are presented below:

![June_Temps.png](Resources/June_Temps.png)  
![December_Temps.png](Resources/December_Temps.png)

## Summary

When comparing June and December data, there is little variation on the maximum temperature, just 2 degrees below in December. The minimum temperature registered in December is 8 degrees lower than June. However, the average temperature presented in December is just slightely lower than June, 71.041529 and 74.944118, respectively. It may indicate that a business reliant on higher temperatures can succeed in this location. 

Still, analysing data from two specific months may not be enough to ensure this business viability. It would be beneficial observe how temperature varies throughout the year, which could be done by quarters. For example:

```
# Filter temperature data from March
session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date)==3).all()

# Filter temperature data from September
session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date)==9).all()
```

Similarly, analysing precipitation info would contribute to understand the potential of a business in the island.

```
# Filter precipitation data for June
session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==6).all()

# Filter precipitation data for December
session.query(Measurement.date, Measurement.prcp).filter(extract('month', Measurement.date)==12).all()
```