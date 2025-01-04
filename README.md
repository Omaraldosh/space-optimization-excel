# space-optimization-excel
integrating and analyzing room booking data with historical usage datasets for The Hague University of Applied Sciences, using Excel. Delivering actionable insights for Measuremen’s workplace analytics.
## Objective
The objective of this project is to:
- Integrate booking and historical usage datasets.
- Apply ETL processes using Power Query for data cleaning and transformation.
- Establish relationships using Power Pivot to enable meaningful analysis.
- Visualize trends and provide actionable insights into space utilization.
## Tools and Technologies
- Microsoft Excel
- Power Query (for ETL: Extract, Transform, Load)
- Power Pivot (for data relationships)
- Data Visualization (using Excel charts)
## Dataset Overview
- **Historical Usage Data:** Includes room type, occupancy, and timestamps.
- **Booking Data:** Contains space type, capacity, faculty, group size, and duration.


## ETL Process in Power Query
### Step 1: Extracting Data from CSV Files
I began by extracting CSV files into Excel through the following steps:

Navigated to the Data Tab: In Excel, I went to the "Data" tab on the ribbon.
Chosen Get Data: I clicked on the "Get Data" button.
Selected From File: I then selected the "From File" option and clicked on "From Text/CSV."
This allowed me to extract the data and load it into Excel for the next steps.
<img width="953" alt="image" src="https://github.com/user-attachments/assets/4fd49567-12ac-4732-ad76-0645dc459fa0" />




### Step 2: Transforming Data in Power Query Editor
Once the data was extracted, I moved to the Power Query Editor for the transformation process.

#### Replacing Blank Values in 'Space Type' Column
I noticed there were blank values in the "space type" column, so my client requested that I replace these blanks with the text "No space Type."

To do this:

In the Power Query Editor, I selected the "Transform" tab.
I used the Replace Values function to replace the blank values with "No space Type."

 ![image](https://github.com/user-attachments/assets/b4e1c366-28eb-4190-86a6-08f78b215ce7)
### Step 3: Handling Blank Values in the 'People Present' Column
Next, I tackled the issue of blank values in the "people present" column. Based on the activity type, I applied different transformations:

If the activity was "Signs of Life" or "Not Occupied", I set the corresponding value in "people present" to 0.
For other activities, I set it to 1.
To implement this, I used the following M Language Code:

m
Copy code
if [Activity] = "Not occupied" or [Activity] = "Signs of life" then 0 
else if [Activity] <> null then 1
As shown in the image, the blank values in the "people present" column were correctly replaced according to the specified conditions.
![image](https://github.com/user-attachments/assets/f1eda236-e1cb-412f-acb8-086af13fbb19)

### After Applied

![Screenshot 2025-01-04 001809](https://github.com/user-attachments/assets/59fae593-01da-486a-9485-e104dc81043c)




Now, with the transformations applied, the dataset is cleaner, with missing values addressed according to the specified rules. This prepares the data for further analysis and reporting.

After preparing and transforming the data in the Power Query Editor, I loaded the dataset using the Close and Load option under the Home tab.

Here’s an illustration of the step in the Power Query Editor:
<img width="814" alt="Screenshot 2025-01-04 191814" src="https://github.com/user-attachments/assets/6c1d0041-46c7-4c6d-b9e3-927e93c06aaa" />


## Data Enhancement with Logical Columns
After loading the transformed data into Excel, I created a new column using an IF Statement. The purpose of this step was to simplify the values in the Activity attribute. Specifically:

Goal: Consolidate all values in the Activity column into two categories:
Occupied: For any activity other than Not Occupied.
Not Occupied: For entries explicitly labeled as such.
This categorization ensures actionable insights and more effective visualizations, focusing solely on occupancy trends.

### Formula and Implementation
Below is an example of the formula applied to create the new column:
<img width="673" alt="Screenshot 2025-01-04 184107" src="https://github.com/user-attachments/assets/49f832f1-08e5-4f47-81d0-ae5747bef28e" />



### Final Outcome
Once the formula was applied, the resulting column successfully categorized the Activity data:
<img width="565" alt="Screenshot 2025-01-04 184423" src="https://github.com/user-attachments/assets/70d3eb13-d08b-40d2-8c98-b35d94eb807d" />


## Integration into Pivot Table
The newly created column was automatically added as a new attribute in the Pivot Table, allowing for dynamic analysis of the Activity data.

By integrating the new Activity column, the Pivot Table now provides a streamlined view of occupancy trends, categorized into Occupied and Not Occupied. Here's how the column appears in the field list of the Pivot Table:

<img width="290" alt="Screenshot 2025-01-04 184558" src="https://github.com/user-attachments/assets/4e0ede01-f88e-4afb-a45a-99bf595b1e43" />


Benefits
Actionable Insights: Quickly analyze and compare the occupancy rates.

Efficiency: Focus on key patterns with simplified categories.

Flexibility: Use the pivot table’s dynamic filtering and sorting options for custom insights.



## Visualizations and Insights
### Question: During Which Time Periods Are Spaces Most Occupied?
With the cleaned and prepared dataset, I created a visualization to explore occupancy patterns across different time periods. This visualization highlights when spaces are most and least utilized, providing valuable insights for optimizing space usage.

### Findings:
Most Occupied Period:
13:00 - 14:00 shows the highest occupancy.
Least Occupied Periods:
08:45 - 10:15 and 16:30 - 18:00 have the lowest occupancy rates.
### Visualization:
Below is the chart demonstrating these occupancy patterns:
<img width="938" alt="Screenshot 2025-01-04 191910" src="https://github.com/user-attachments/assets/dab4253a-2733-4354-9407-ae403a0746e2" />


### Impact:
Planning Efficiency: Insights can help allocate resources effectively and schedule activities during peak usage times.

Optimization: Identify underutilized spaces for potential repurposing during off-peak hours








