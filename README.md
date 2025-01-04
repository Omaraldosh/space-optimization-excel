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
