# Parking Violations In The District of Columbia

This project was done in collaboration with two other classmates for a class. 

## Business Application

* What conclusions can be made regarding the parking violations that occur in DC?
* Find common parking violation spots in order to improve city parking in the DC area.
* City planners will use our application to find the best parking garage spots as well as other parking solutions.

## Predictions

* We predicted that weekends would have the most parking violations
* We predicted that most of the parking violations would occur near the Capital
* We predicted that most violations would be under “No Parking”

## Dataset - Parking Violations for District of Columbia

* Parking Violations issued by DC Metropolitan Police Department
* Summarized ticket counts based on time and category
* Retrieved from DC DMV management system
* May not be most reliable source
  * No Authors (The dataset was shared by user DCGISopendata)
* File formatting was bare bones
* Unknown License

![Kaggle Score](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure1.png)

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

## Unsupervised Approach:

* Stripping misclassified entries
  * Removed Null Values
  * Removed unneeded columns (X coord, Y coord, Week of month, Month of year, Plate (state),X (num), Y (num), body style

## Algorithm(s) Used

* SUCCESSFUL:
  * K-Clustering (using 4 clusters):
  * J48 Decision Tree
* UNSUCCESSFUL:
  * Apriori Association
  * K clustering exceeding 4 clusters (software/hardware shortcomings)
  * ZeroR
  * OneR

## K-Clustering Results

![K-Clustering Result](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure2.png)
![K-Clustering Result](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure3.png)

Days of the Week w/ Location
![K-Clustering Result](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure5.png)

## J-48 Result

![J-48 Result](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure4.png)

## Issues Encountered

* The Weka application kept generating heap errors, so some of the algorithms we wanted to use were unusable.
* Some of the Algorithms we tried (ZeroR, OneR) either kept generating 100% correctly classified results or a subpar (<50%) correctly classified results.
* The dataset we used could not utilize Apriori association, so we weren't able to use an association algorithm.

## Data Visualization: Types of Violations

![Types of Violations](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure6.png)

## Data Visualization: Days with the Most Parking Violations

![Days with the Most Parking Violations](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure7.png)

## Data Visualization: Weekends w/ Locations

* Wednesday <br/>
![Wednesday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure8.png)

* Tuesday <br/>
![Tuesday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure9.png)

* Thursday <br/>
![Thursday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure10.png)

* Saturday <br/>
![Saturday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure11.png)

* Sunday <br/>
![Sunday](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure12.png)


## Data Visualization: Locations with the Most Violations

![Locations with the Most Violations](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure13.png)

## Data Visualization: Top 3 Most Ticketed Streets

* #1 - 300 Block C ST NW North Side <br/>
![](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure14.png)

* #2 - 1300 Block G ST NW North Side <br/>
![](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure15.png)

* # 3 - 1300 Block K ST NW North Side <br/>
![](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure16.png)

## 
![](https://github.com/sauthh/parking-violations-in-the-district-of-columbia/blob/5660a03183bf19a5f363f054f9f0211633d53147/Figures/figure17.png)
