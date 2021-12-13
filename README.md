# ExcelChallenge
## Project Overview
### Purpose
The purpose of this week’s assignment was to explore the capabilities of Microsoft Excel to organize, analyze, and display data through tables and charts.  
### Data Analyzed
The specific dataset I analyzed included campaign information from various Kickstarter campaigns launched across the world from 2009-2017.  Variables of most interest for the deliverables of this assignment included Campaign Name, Fundraising Goal, Outcome, Launch Date, and Category/Subcategory.  
### Deliverables
For Deliverable 1, I created a pivot table and line chart to portray “theater” campaign outcomes based on their launch date.  
For Deliverable 2, I created a new sheet and a line chart to display “play” campaign outcomes based on their goal range.  

## Analysis and Challenges
### Deliverable 1 Analysis
1.	Through in-class and pre-work module activities, I had already created four new columns: Parent Category, Sub Category, Deadline Launch Date Converted, and Launch Date Converted.  

![image](https://user-images.githubusercontent.com/92705556/145734203-a508e1c1-08e2-42a9-808a-c0ac9c97f2db.png)

- Parent and Sub Category columns were created on the “Category and Subcategory” column using Data Tools “Text to Columns”, Delimited, Other: /
- Deadline and Launch Date conversions were preformed on the “deadline” (I) and “launched_at”  (J) columns using the formula =(((value/60)/60)/24)+DATE(1970,1,1).  Value is the corresponding cell value in either the deadline or launched_at column
2.	To create a “Years” column for launch date, I used the formula =YEAR(value). Value is the corresponding cell value in the Launched Date Converted column.  
3.	I next selected all data in the chart and created a pivot table on a new sheet by going to Insert, PivotTable.  I then renamed the new sheet “Theater Outcomes Launch.
- Within the PivotTable Fields, I added “Parent Category” and “Year” to the Filters section of the pivot table.  
  - I filtered the Parent Category to only include “Theater”.

![image](https://user-images.githubusercontent.com/92705556/145734246-d6ba632b-8378-413f-8aea-f85f30e760fe.png)

- I also added “Outcomes” to Columns, “Launch Date Converted” to Rows, and “Outcomes” to Values.  
  - I then changed the value field setting from sum to count.
  - I also filtered Outcomes to only include successful, failed, and canceled (not including live).
4.	Next, I inserted a Line PivotChart under Insert, PivotChart, Line with Markers.
-	Month is displayed on the x-axis and Number of Outcomes is displayed on the y-axis
 
 ![image](https://user-images.githubusercontent.com/92705556/145734253-a19ef546-ecd0-4a37-bf29-c7e76f45fd43.png)

### Deliverable 2 Analysis
1.	I created a new sheet and renamed it “Outcomes Based on Goal”.
2.	I added columns for Goal, # (Number) Successful, # Failed, # Canceled, Total Projects, % (Percentage) Successful, % Failed, & % Canceled, as directed by the instructions.
- I also added three additional columns for my own use in formulas: Lower Range, Upper Range, and Count.

![image](https://user-images.githubusercontent.com/92705556/145734304-228f3ebc-b778-4ca3-89db-e1b33c908a98.png)

3.	To determine the # of Successful, failed, and canceled “play” campaign, I used the formula below for each respective column. =COUNTIFS('Kickstarter Data'!$D:$D,">="&$B2,'Kickstarter Data'!$D:$D,"<="&$C2,'Kickstarter Data'!$P:$P,"="&"plays",'Kickstarter Data'!$F:$F,"="&"successful")
- This formula drew goal, subcategory, and outcome information from the original Kickstarter datasheet and compared it to upper and lower goal limits to count how many plays were successful, failed, and canceled.  
- The COUNTIF formula allowed for multiple variables/criteria to be analyzed at once.  
- Note: the last criteria of the formula, “outcome”, changed with each respective column (E,F,G).
4.	The Total Projects column was determined using the formula =sum(E2:G2).   Cells changed with each respective row.
5.	The percentage columns were created using the formula =E2/$H2*100.  Cells changed with each respective row and column.
6.	While a Pivot Table was not required, I chose to make a pivot table nevertheless.  Furthermore, a PivotChart was not required (just a line graph was); however, I chose to make a Line PivotChart from my PivotTable with goal range on the x-axis and Percentage of Outcomes on the y-axis. The resulting PivotChart would look the same as if I had done a regular line chart.

![image](https://user-images.githubusercontent.com/92705556/145734319-306c1c3f-06cf-4a47-a1e2-bb438db4ba29.png)

### Deliverable 1 and 2 Challenges
I am fairly comfortable in Excel, thus I did not have any challenges with either Deliverables.  That being said, I could see that challenges could exist if you did not know how to use formulas to determine unknown values, if you were  unfamiliar with pivot tables or how to add charts (whether regular line charts or PivotCharts).

## Results
### Theater Outcomes by Launch Date 
From the data and resulting pivot table and line graph, I conclude that May is the most common month for releasing theater production (highest total of all outcomes regardless of success rate).  May also has the highest number of successful outcomes.  If it were me, I would not release a theater production in December because that is the month with the fewest successful outcomes, and the number of failed outcomes nearly matches successful ones.  I hypothesize that this is a result of holiday gatherings, parties, and chaos.

### Play Outcomes Based on Goals
From the depicted data and graph, it appears that there two goal ranges that tend to produce the most successful and least failed outcomes.  Those ranges are $0-4,999 and $35,000-45,000.  These ranges suggested two different types of most successful plays: 1) very low production cost plays and 2) a few moderately-high production cost plays.  I hypothesize that very low production cost (shoestring budget) plays are successful because almost no income is needed to make the play a success.   I also hypothesize that a production cost of $35,000-45,000 but be a “sweet-spot” figure that allows for decent success based on cost of production.  

### Limitations and Additional Analysis
While the required deliverables placed certain limitations on the ability to explore and analyze the dataset, I believe the dataset, as a whole, allows for many additional analyses to be performed.  In fact, I performed some of these on my own.  Using Outcomes by Launch Date data, I would (and did) portray outcomes by year rather than month.  This allows you to see that 2015 was the most productive year for theater productions.  I also reassessed the month data to show stacked columns of % outcomes by month.  

![image](https://user-images.githubusercontent.com/92705556/145734378-c44f6a90-940e-4206-a515-feace0f038f6.png)

![image](https://user-images.githubusercontent.com/92705556/145734381-0cf90565-ce04-4f1d-b48a-3fbd88bccd77.png)

Though I did not perform data analysis on it, I think it would be intersesting to:
1.	Plot success by country
2.	Plot success by Parent Category (showing all categories, not just theater)
