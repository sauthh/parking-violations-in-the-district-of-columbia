# Parking Violations In The District of Columbia

This project was done in collaboration with Devon Sellers and Colin Hill for the course IS425 – Decision Support Systems at UMBC.

## Dataset - Parking Violations for District of Columbia

* Parking Violations issued by DC Metropolitan Police Department
* Summarized ticket counts based on time and category
* Retrieved from DC DMV management system
* May not be most reliable source
  * No Authors (The dataset was shared by user DCGISopendata)
* File formatting was bare
* Unknown License

![Kaggle Score](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure1.png)

Figure 1 - Kaggle file overview

## Dataset (132,850 rows)

* OBJECTID (unique ID)
* RP_PLATE_STATE (text)
* ROWID_ (unique ID)
* BODY_STYLE (text)
* DAY_OF_WEEK (text)
* ADDRESS_ID (number)
* HOLIDAY (number)
* STREETSEGID (number)
* WEEK_OF_YEAR (number)
* XCOORD (number)
* MONTH_OF_YEAR (number)
* YCOORD (number)
* ISSUE_TIME (number)
* TICKET_ISSUE_DATE (date)
* VIOLATION_CODE (text)
* X (coordinates)
* VIOLATION_DESCRIPTION (text)
* Y (coordinates)
* LOCATION (text)

## Predictions

* We predicted that weekends would have the most parking violations
* We predicted that most of the parking violations would occur near the Capital
* We predicted that most violations would be under “No Parking”

## Approach

In order to analyze the data, we decided to use a descriptive approach for parking violations using K-clustering and association rules. These methods helped us determine what the most parking violations consisted of and when they took place. Then, we used a predictive approach to figure out which areas of DC were prone to the most traffic violations and where new parking locations should be located.

## Algorithms Used
To start, we used a K-clustering algorithm to determine which violation descriptions had the most amount of violations associated with them.
* First, we pre-processed our data by stripping Misclassified entries (outliers).
* Finally, we applied K clustering to our data and were able to see that our data contained 2 clusters.

Then, We used a K clustering algorithm to determine which day of the week had the most parking violations associated with it. Finally, we used association rules to determine if the parking violations were consistent throughout the year or if they were influenced by weather, seasons, events, or other various factors.

* SUCCESSFUL:
  * K-Clustering (using 4 clusters):
  * J48 Decision Tree
* UNSUCCESSFUL:
  * Apriori Association
  * K clustering exceeding 4 clusters (software/hardware shortcomings)
  * ZeroR
  * OneR

## Metrics Used
We used K-means clustering that consisted of a maximum of 500 iterations, a maximum of 5 number clusters, and 1 execution slot. For our classifications, we used a batch size of 100, 3 folds, and 1 seed. In our analysis, we kept reduced error pruning to false to get the full picture without cutting out necessary parts of the data set.

## Results of Analytics

With the help of Tableau, we discovered that the top five reasons for parking violations were parking at expired meters, failure to display a multi-space meter receipt, disobeying an official sign, residential permit parking beyond the limit without a permit, and no stopping or standing in PM rush hour zone. As can be seen with figure 15, the first two reasons are considerably higher than the rest and the next two are similar in amount. Furthermore, we found that the top places where tickets were given out the most were 300 Block C Street NW east side, 1300 Block K Street NW north side, 1300 Block G Street NW north side, 1000 block Thomas Jefferson Street NW, and 1300 block H Street NE south side. Upon viewing our results [Figure 11](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_8.png), it appears that the 1300 block has three out of the five most ticketed areas of the DC area. Thus, this would be a great section of the city to develop more parking infrastructure. Lastly, we also found that Wednesday, Tuesday, and Thursday were the days where tickets were given out the most, which could be seen in figure 4. It makes sense as people do not go out on Sundays and Saturdays very often. Additionally, people will start going to work on Mondays, so the rise makes sense and fewer people are out on Fridays, so the decrease is also valid.

![k-4 cluster results](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/ab4c70a266c8fd84cce7e636446723940da1d025/Figures/img_13.png)

Figure 2 - k-4 cluster results

On the algorithm side we used four clusters. The data we are looking for includes: parking violation reason, violation location, and ticket issue date. All these results come from Image 3.  Cluster one had: Fail to display a multispace meter receipt, 1300 Block H ST NE South Side, 2015-12-09. Cluster two had: Park at expired meter, 1000 Block Thomas Jefferson St NW, 2015-12-16. Cluster three had Park at expired meter, 1600 Block P St Nw North Side, 2015- 12-10. Cluster four had: disobeyed an official sign, 1400 Block S ST NW North Side, 2015-12-22. Using these clusters, we can cross reference the data acquired on weka with the data we acquired using tableau. In both applications, 1000 block Thomas Jefferson Street NW was in both data sets, so this would be an optimal location to build new parking infrastructure. We also noticed that two out of the four clusters had “park at expired meter” as the reason for the ticket, so with this knowledge, we can predict that parking over the limit of a meter is a common issue in DC. Thus, parking garages could help alleviate this problem, especially on Thomas Jefferson Street. 

![Days with the most parking violations](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/ab4c70a266c8fd84cce7e636446723940da1d025/Figures/img_0.png)

Figure 3 - Days with the most parking violations

We observed that the weekends have the least violations while the middle of the week tends to have the most violations. On the other hand, we observed that Tuesday, Wednesday, and Thursday have the most violations. This is consistent with our expectations, as the majority of the population works during the weekdays, so traffic will be consistently high compared to occasional special events on weekends

![Most Violations on Sunday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_1.png)

Figure 4 - Most Violations on Sunday

This image shows the different violations on Sunday. The biggest reason was disobeying official signs and parking in illegal places. Sunday has the least amount of infrastructure and also differs quite a bit compared to the rest.

![Most Violations on Monday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_2.png)

Figure 5 - Most Violations on Monday

Parking at an expired meter, failing to display a multispace meter receipt, and residential permit parking beyond limit without permit were the biggest reasons. This is similar to other days, where people committed similar violations.

![Most Violations on Tuesday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_3.png)

Figure 6 - Most Violations on Tuesday

Parking at an expired meter, failing to display a multispace meter receipt, and residential permit parking beyond limit without permit were the biggest reasons. This is similar to other days, where people committed similar violations. 

![Most Violations on Wednesday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_4.png)

Figure 7 - Most Violations on Wednesday

Parking at an expired meter, failing to display a multispace meter receipt, and residential permit parking beyond limit without permit were the biggest reasons. This is similar to other days, where people committed similar violations. 

![Most Violations on Thursday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_5.png)

Figure 8 - Most Violations on Thursday

Parking at an expired meter, failing to display a multispace meter receipt, and residential permit parking beyond limit without permit were the biggest reasons. This is similar to other days, where people committed similar violations. 

![Most Violations on Friday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_6.png)

Figure 9 - Most Violations on Friday

Parking at an expired meter, failing to display a multispace meter receipt, and disobeying official signs. The two first violations were similar except the third one, which we can guess that people were likely in a hurry to go home and did not see road signs.

![Most Violations on Saturday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_7.png)

Figure 10 - Most Violations on Saturday

The biggest reasons were parking at expired meters, failing to display a multispace meter receipt and disobeying official signs. Based on the statistics, it seems Saturday had similar outcomes compared to Friday, but slightly less in all fields.

![Locations with the Most Violations](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_8.png)

Figure 11 - Locations with the Most Violations

“300 Block C ST NW North Side” has vastly more compared to others. A simple Google search shows that it is located right next to E. Barrett Prettyman United States Courthouse, and while the irony of receiving a ticket parking violation at a courthouse is not lost on us, it does provide us with a potential location that may warrant a recommendation for additional parking facilities. “1300 Block K ST NW North Side” is located near a public park and “1300 Block G ST NW North Side” is located near a Metro Station. For both instances, we have high-traffic areas where the public may need additional parking services to accommodate the amount of individuals using them.

![Most Violations at “300 Block C ST NW North Side”](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_9.png)

Figure 12 - Most Violations at “300 Block C ST NW North Side”

Figure 12 shows why people were ticketed so often near the courthouse. The biggest reason was “Unauthorized Vehicle in Loading Zone” because people, most likely, drove to the courthouse to quickly pick up someone but ended up being ticketed instead. Additionally, the previous explanation also holds true for the next highest reason, which is“Park in Reserved Space for Motorcycles Only.”

![Most Violations at “300 Block C ST NW North Side”](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_10.png)

Figure 13 - Most Violations at “1300 Block K ST NW North Side”

The biggest reason out of everything was parking overtime at the meter, which makes sense because people probably intended to park for a couple of hours but ended up parking overtime as they could have been too busy at the park or at the “Paul” restaurant. This reason consisted of double the amount of the second highest reason, which was failure to display at a multi-space meter receipt. The last notable reason was that the expiration time on a meter receipt had expired.  

![Most Violations at “1300 Block G ST NW North Side”](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_11.png)

Figure 14 - Most Violations at “1300 Block G ST NW North Side”

The two biggest reasons were failing to display a multi-space meter receipt and unauthorized vehicles in the loading zone. Since the street is near multiple stores and a metro station, we can guess that people were in a hurry and simply forgot to put their receipts in the front. Additionally, people might have thought to pick up friends/family members quickly, so they most likely stopped at a loading zone without thinking much.

![Types of Violations](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/da941d6d2b8127c810ad4f49df326e5f4855d622/Figures/img_12.png)

Figure 15 - Types of Violations

The biggest reason we observed was parking at an expired meter with around 18k tickets issued. The second biggest reason was failing to display a multi-space meter receipt at around 15k tickets issued. The third biggest reason was disobeying an official sign at around 10k tickets issued. Finally, the fourth biggest reason was parking at a residential parking permit spot beyond the limit without a permit. These trends help solidify our observation that most of the time, people just tend to forget whether it be putting up their receipt or remembering how long they put the parking meter for.

## Decision Question
The graphs helped answer some of our burning questions such as “What was the biggest reason for parking violations?”, “Where were people being fined the most”, “In the places where people were fined, what was the violation and why?”, “What time of the week were people most likely to be fine”, etc. 

All of these questions were answered using solely the data portion of our project, not any weka results were included. Thus, we weren't able to use any of the Weka applications benefits such as association rules and decision algorithms.  Using these, we could have found more unknown correlations and patterns to help make the best decisions for parking in the DC area. 

## Successes and Failures
While doing this deliverable, running the dataset through Weka gave us a lot of failures. For example, doing a k-means algorithm consistently gave us very high incorrect cluster occurrences. It meant that we had improper parameters for it and our data was labeled, so it couldn’t cluster them properly. Additionally, We found that given our particular data set we were unable to run association analysis, as the Apriori Associator was not compatible with the data set we are using, and results are not applicable. Specifically, Apriori could not handle the numeric attributes within our data set. However, in terms of success, using Tableau was considerably easier, so we were able to learn basic statistics about our dataset easily. It also helped to organize the data by using different graphs, which made the process faster.

When using K clustering, we noticed that a k value of 4 was the most consistent in terms of getting reliable data. Anything higher would result in a higher incorrect accuracy. Anything less would also give us a less accurate model of our data.

## Conclusion

* Our predictions were mostly false
* We predicted weekends would have the most violations
  * Tuesdays and Wednesdays had the most violations
* We predicted most violations would occur near the capital
  * This held true
* We predicted that most violations would be under “No Parking”
  * Most parking violations were due to expired meter parking
* We can recommend additional parking locations, but emphasis on individuals paying for existing parking should be primary focus to reduce parking violations
  * This can be concluded from our observations from violation types and what days the violations occur

## Reference

https://www.kaggle.com/datasets/arcgisopendata/dc-parking-violations
