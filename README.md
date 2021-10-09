# surfs_up
Module 9 - SQLite, Flask

## Overview
This analysis was prepared to offer insights for a business plan. A proposed 'Surf and Ice Cream' business needs to understand the weather of the potential locations of their store. As Oahu is the owner's primary focu, this analysis analyzed weather trends in December in January to make sure the business would be sustainable year-round. 

## Results
Below are the summary statistics for June and December weather in Oahu. The following insights can be determined from the deliverables:
* The average temperature in December (71) is not signficantly colder than in June (74), a positive sign for the business prospects. 
* The minimum temperature is 64 in June and 56 in December. 
* The owner can expect a majority of December to be between 69 and 73, temperatures that should support demand for his business.

June Results

![image](https://user-images.githubusercontent.com/85259984/136672816-0d69b0b8-22a5-42db-abed-db1b87aaa8c9.png)

December Results

![image](https://user-images.githubusercontent.com/85259984/136672804-e54b677a-ad9f-4c47-9111-e78bd260da6c.png)


## Summary
The results of this analysis indicate that the business should see year-round demand in Oahu. The following queries can also be used to help inform this business decision:

* dec_coldrain = session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date) == 12, Measurement.tobs < 70, Measurement.prcp >= 0.1).all()
* june_coldrain = session.query(Measurement.date, Measurement.tobs).filter(extract('month', Measurement.date) == 6, Measurement.tobs < 70, Measurement.prcp >= 0.1).all()

While the summary statistics offer a positive outlook on weather in Oahu, these queries will allow the owner to understand how often days will occur where ice cream demand will be low. The criteria for low demand was considered a temperature below 70 degress and precipitation totals over 0.1. By running the above queries and looking at the length of each list, it can be seen that the owner should expect ~3x as many days of low demand as they will in June. This should be factored to any forecasts for revenue in December. The results of these queries can be seen in the "SurfsUp_Challenge" Jupyter Notebook. 
