# Call-centre-Trend
Possible KPIs include (to get you started, but not limited to):  Overall customer satisfaction Overall calls answered/abandoned Calls by time Average speed of answer Agent’s performance quadrant -> average handle time (talk duration) vs calls answered



Creating a dashboard in Power BI for call center trends involves several steps to visualize the relevant KPIs and metrics from your dataset. Here’s a guide to help you build this dashboard:

Step 1: Prepare Your Data
Load the Data:

Open Power BI Desktop.

Click on Get Data and select Excel.

Locate and load the 01 Call-Center-Dataset (1).xlsx file.

Data Cleaning:

Check for missing values, especially in crucial columns like Answered (Y/N), Resolved, and Satisfaction rating.

Remove or fill any missing entries as necessary.

Data Transformation:

Convert the AvgTalkDuration from hh:mm:ss format to a numerical format (in seconds) for calculations.

Create a new column for Call Date if it doesn’t exist by combining Date and Time.

Ensure that columns like Satisfaction rating are in numeric format.


Step 2: Define KPIs and Metrics


Customer Satisfaction:
Create a measure to calculate overall customer satisfaction:
dax
Overall Satisfaction = AVERAGE('Sheet1'[Satisfaction rating])


Calls Answered vs. Abandoned:
Create measures for total calls answered and total calls abandoned:
dax

Total Calls Answered = COUNTROWS(FILTER('Sheet1', 'Sheet1'[Answered (Y/N)] = "Y"))

Total Calls Abandoned = COUNTROWS(FILTER('Sheet1', 'Sheet1'[Answered (Y/N)] = "N"))



Average Speed of Answer:
Create a measure for average speed of answer:
dax
Avg Speed of Answer = AVERAGE('Sheet1'[Speed of answer in seconds])

Calls by Time:
Create a time bucket measure for calls, e.g., hourly or by half-hour intervals, to analyze call volume throughout the day.
Agent Performance Quadrant:


Create measures for average handle time and total calls answered by each agent:
dax

Avg Handle Time = AVERAGE('Sheet1'[AvgTalkDuration])




Step 3: Build the Dashboard
Create Visualizations:
Card Visuals: Use card visuals to display key metrics like overall customer satisfaction, total calls answered, and average speed of answer.
Bar/Column Charts: Display call volume by time (using your time bucket) and calls answered vs. abandoned.
Scatter Plot: For the agent performance quadrant, use a scatter plot with Avg Handle Time on one axis and Calls Answered on the other.
Add Filters:
Add slicers for agent names, call topics, and date ranges to allow detailed analysis.
Customize Layout:
Arrange visuals in a clean, logical layout. For example, place key metrics at the top and more detailed charts below.
Use consistent color themes to enhance readability.




Step 4: Review and Publish
Review Your Dashboard:
Ensure all visuals are displaying correctly and that measures are calculating as intended.
Check for responsiveness on different screen sizes.
Publish the Dashboard:
Click on Publish to share your dashboard with your team or management.




Step 5: Prepare for Discussion
Insights:
Prepare insights based on the data, such as trends in customer satisfaction over time, call response times, and agent performance.
Highlight any areas for improvement, such as high abandoned call rates or low satisfaction scores.
Discussion Points:
Be ready to discuss potential strategies for improving customer satisfaction and reducing call abandonment.

