# 📊 **Space Optimization in Excel**
This project analyzes room usage at The Hague University of Applied Sciences based purely on **Observation Data** provided by **Measuremen**. The goal is to provide **innovative insights** into **space utilization** through **Excel** by leveraging powerful data transformations and visualizations. ✨

## 🚀 **Project Objective**
The main goals of this project are:
- Analyze historical space utilization patterns based on **observed** data.
- **Clean** and **transform** the data using **Power Query** (ETL process).
- Offer actionable insights to optimize space and improve efficiency across university campuses. 🌍

## 🛠️ **Tools and Technologies**
- **Microsoft Excel** 🧑‍💻
- **Power Query** (for **ETL**: Extract, Transform, Load) ⚙️
- **Excel Visualizations** 📊

## 📝 **Dataset Overview**
The observation data is provided by Measuremen and includes:
- Space types 🏢
- Room occupancy 🧑‍🤝‍🧑
- Number of people present 👥
- Activity types 🕓

---

## 🔄 **ETL Process in Power Query**

### 1️⃣ **Extracting Data from CSV Files**
The observation data is imported into Excel using Power Query:
1. Go to the **Data** tab in Excel.
2. Use **Get Data** and select **From File > From Text/CSV** to load the data. 🚀

<img width="953" alt="image" src="https://github.com/user-attachments/assets/4fd49567-12ac-4732-ad76-0645dc459fa0" />

### 2️⃣ **Transforming Data in Power Query Editor**

I applied essential transformations:

- **Replacing Blank Space Types**:
  I replaced blank values in the **'space type'** column with the value “No space Type” for clarity. 🏚️ ➔ 🏢
  
![image](https://github.com/user-attachments/assets/b4e1c366-28eb-4190-86a6-08f78b215ce7)

- **Handling Missing People Count**:
  I used a condition to handle blank values in the **people present** column based on the activity type:
  - “**Signs of Life**” and “**Not Occupied**” -> Set people present to **0**.
  - Other activities -> Set to **1**.

    The formula in **M Language**:
    ```m
    if [Activity] = "Not occupied" or [Activity] = "Signs of life" then 0 
    else if [Activity] <> null then 1
    ```

   ![image](https://github.com/user-attachments/assets/f1eda236-e1cb-412f-acb8-086af13fbb19)
  ### After Applied
  ![Screenshot 2025-01-04 001809](https://github.com/user-attachments/assets/59fae593-01da-486a-9485-e104dc81043c)

### 3️⃣ **Loading Transformed Data into Excel**
Once the data was cleaned and transformed, it was loaded back into Excel for deeper analysis using the **"Close and Load"** function in Power Query. ✅

<img width="814" alt="Screenshot 2025-01-04 191814" src="https://github.com/user-attachments/assets/6c1d0041-46c7-4c6d-b9e3-927e93c06aaa" />

---

## 📑 **Data Enhancements with Logical Columns**

After transformation, I created logical columns to classify **"Activity"** into:
- **Occupied** 🔒
- **Not Occupied** 🚫

This made analysis much simpler and more straightforward. 🎯

    Formula used for this:
    ```excel
    =IF(Activity = "Not Occupied", "Not Occupied", "Occupied")
    ```

   <img width="673" alt="Screenshot 2025-01-04 184107" src="https://github.com/user-attachments/assets/49f832f1-08e5-4f47-81d0-ae5747bef28e" />
   
### Final Outcome

   <img width="565" alt="Screenshot 2025-01-04 184423" src="https://github.com/user-attachments/assets/70d3eb13-d08b-40d2-8c98-b35d94eb807d" />
---

## 🔍 **Key Insights and Visualizations**

### 📅 **Occupancy Across Time Periods**
I analyzed which hours had the highest and lowest occupancy:
- **Most Occupied Period**: 13:00 - 14:00 🕐💼
- **Least Occupied Period**: 08:45 - 10:15 & 16:30 - 18:00 🕓🕔

<img width="938" alt="Screenshot 2025-01-04 191910" src="https://github.com/user-attachments/assets/dab4253a-2733-4354-9407-ae403a0746e2" />

### 💡 **Impact:**
- Understanding these times helps allocate resources efficiently. 🌍
- Highlight areas that may need repurposing during low-usage periods.

### 🏢 **Space Utilization: People vs. Capacity**
I compared the number of people present to the **room capacity** to analyze whether spaces are being underutilized:
- **Underutilization:** Capacity often exceeds occupancy by more than 50%! 📊❗

<img width="925" alt="image" src="https://github.com/user-attachments/assets/81599954-0821-4a1b-9732-8a2f4a97e5e2" />

### 📉 **Impact:**
- Optimizing underused spaces for **better resource allocation**. 🔄

### 🏫 **Campus Occupancy Comparison**
- Analyzed which campuses had the highest and lowest occupancy rates.
  - **Delft Campus** 🌍: 42% occupancy 📈
  - **Delft Beta Factory** 🏢: 30% occupancy 📉

<img width="902" alt="image" src="https://github.com/user-attachments/assets/720d3da2-6e0f-4796-b514-3e0d044c74d2" />

### 📅 **Impact:**
- Useful for **campus planning**: Space allocation based on **actual demand**.

### 📅 **Occupancy Trends Across Weekdays**
The study revealed interesting trends based on weekdays:
- **Monday, Tuesday, Thursday** 📅: High occupancy.
- **Friday** 🗓️: Low occupancy, meaning rooms might be underused on that day.

<img width="890" alt="image" src="https://github.com/user-attachments/assets/5bf1818e-19fe-41ce-b18f-9a9308af4855" />

### 📅 **Impact:**
- This data can help tweak **class schedules** or explore activities suited for lower occupancy days. 🔄

---

## 📊 **Visualization Breakdown**
1. **Occupancy Line Charts** 📉
    - Understand when most and least spaces are occupied across hours and days.
 
  
2. **Pivot Tables** 📅
    - Quickly compare and filter occupancy data to reveal trends and outliers.
    

3. **Bar and Pie Charts** 📊
    - Highlight campus utilization rates for better decision-making. 🏫
    

---

### 🌟 **Conclusion**
This project provided actionable insights into space optimization, leading to better resource planning and potentially improving sustainability. It also demonstrates how using **Excel** and **Power Query** can streamline data management processes. ⚡

💬 Feel free to explore the code and visualizations to dive deeper into the world of data-driven space planning! 🌍📊
