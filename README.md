#Parking Violations In The District of Columbia

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
  * K clustering (using 4 clusters):
  * J48 Decision Tree
* UNSUCCESSFUL:
  * Apriori Association
  * K clustering exceeding 4 clusters (software/hardware shortcomings)
  * ZeroR
  * OneR

## 
