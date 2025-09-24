# Parking Violations In The District of Columbia

This project was done in collaboration with two other classmates, Devon Sellers and Colin Hill, for the course IS425 – Decision Support Systems at UMBC.

## Dataset - Parking Violations for District of Columbia

* Parking Violations issued by DC Metropolitan Police Department
* Summarized ticket counts based on time and category
* Retrieved from DC DMV management system
* May not be most reliable source
  * No Authors (The dataset was shared by user DCGISopendata)
* File formatting was bare bones
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

## Algorithm(s) Used

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

[Figures/img_0.png](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5fe20db26da6539fbdb27020e8ea5b52416566ae/Figures/img_0.png)
Figure 2 - Days with the most parking violations

https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5fe20db26da6539fbdb27020e8ea5b52416566ae/Figures/img_1.png



With the help of Tableau, we discovered that the top five reasons for parking violations were parking at expired meters, failure to display a multi-space meter receipt, disobeying an official sign, residential permit parking beyond the limit without a permit, and no stopping or standing in PM rush hour zone. As can be seen with Image 1, the first two reasons are 2 considerably higher than the rest and the next two are similar in amount. Furthermore, we found that the top places where tickets were given out the most were 300 Block C Street NW east side, 1300 Block K Street NW north side, 1300 Block G Street NW north side, 1000 block Thomas Jefferson Street NW, and 1300 block H Street NE south side. Upon viewing our results (Image 2), it appears that the 1300 block has three out of the five most ticketed areas of the DC area. Thus, this would be a great section of the city to develop more parking infrastructure. Lastly, we also found that Wednesday, Tuesday, and Thursday were the days where tickets were given out the most, which could be seen in Image 3. It makes sense as people do not go out on Sundays and Saturdays very often. Additionally, people will start going to work on Mondays, so the rise makes sense and fewer people are out on Fridays, so the decrease is also valid.

On the algorithm side we used four clusters. The data we are looking for includes: parking violation reason, violation location, and ticket issue date. All these results come from Image 12. Cluster one had: Fail to display a multispace meter receipt, 1300 Block H ST NE South Side, 2015-12-09. Cluster two had: Park at expired meter, 1000 Block Thomas Jefferson St NW, 2015-12-16. Cluster three had Park at expired meter, 1600 Block P St Nw North Side, 2015- 12-10. Cluster four had disobeyed an official sign, 1400 Block S ST NW North Side, 2015-12-22. Using these clusters, we can cross reference the data acquired on weka with the data we acquired using tableau. In both applications, 1000 block Thomas Jefferson Street NW was in both data sets, so this would be an optimal location to build new parking infrastructure. We also noticed that two out of the four clusters had “park at expired meter” as the reason for the ticket, so with this knowledge, we can predict that parking over the limit of a meter is a common issue in DC. Thus, parking garages could help alleviate this problem, especially on Thomas Jefferson Street.

## Successes and Failures
While doing this deliverable, running the dataset through Weka gave us a lot of failures. For example, doing a k-means algorithm consistently gave us very high incorrect cluster occurrences. It meant that we had improper parameters for it and our data was labeled, so it couldn’t cluster them properly. Additionally, We found that given our particular data set we were unable to run association analysis, as the Apriori Associator was not compatible with the data set we are using, and results are not applicable. Specifically, Apriori could not handle the numeric attributes within our data set. However, in terms of success, using Tableau was considerably easier, so we were able to learn basic statistics about our dataset easily. It also helped to organize the data by using different graphs, which made the process faster.

When using K clustering, we noticed that a k value of 4 was the most consistent in terms
of getting reliable data. Anything higher would result in a higher incorrect accuracy. Anything
less would also give us a less accurate model of our data.

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
