# Midterm-Task-2 Data Cleaning and Transformation Using Power Query Editor


This task demonstrates the process of data cleaning and preparation using Power Query. The dataset consists of multiple related tables, where cleaning techniques are applied to improve data quality and consistency before analysis.

## Step-by-Step Process
### Step 1: Download and Load Data  
1. Download the dataset (Uncleaned_DS_jobs.csv)  
2. Open Excel  
3. Go to Data → New Query → Open File → Text/CSV  
4. Click Load and then Edit using Power Query Editor  

### Step 2: Duplicate Raw Data  
1. Right-click the dataset in the Queries pane  
2. Select Duplicate  

### Step 3: Clean Salary Data  
1. Select the Salary Estimate column  
2. Go to Transform Menu → Extract → Text Before Delimiter  
3. Type "(" and click OK  
4. Create two new columns: Min Salary and Max Salary  
   - Select Salary Estimate column → Add Column Menu → Column from Examples → From Selections  
   - Type the first min salary value and press Enter (all rows will auto-fill)  
   - Rename the column to "Min Sal"  
   - Repeat the process for Max Salary  

### Step 4: Add Role Type Column  
1. Go to Add Column Menu → Custom Column  
2. Rename the column to "Role Type"  
3. Use this logic:  
   - If Job Title contains "Data Scientist" → Assign "Data Scientist"  
   - If Job Title contains "Data Analyst" → Assign "Data Analyst"  
   - If Job Title contains "Data Engineer" → Assign "Data Engineer"  
   - If Job Title contains "Machine Learning" → Assign "Machine Learning Engineer"  
   - Otherwise, assign "Other"  
4. Change the column type to Text  

### Step 5: Split Location Column  
1. Select the Location column  
2. Add a Custom Column with corrections:  
   - If Location = "New Jersey" → Assign ", NJ"  
   - If Location = "Remote" or "United States" → Assign ", Other"  
   - If Location = "Texas" → Assign ", TX"  
   - If Location = "California" → Assign ", CA"  
3. Click OK, then select the new column  
4. Go to Transform → Split Column → By Delimiter (comma ",")  
5. Click OK  
6. Rename the second split column to "State Abbreviations"  
7. Check and replace incorrect values (e.g., "Anne Rundell" → "MA")  

### Step 6: Split Size Column  
1. Create two new columns: MinCompanySize and MaxCompanySize  
2. Use the same method as Salary Estimate to split values  

### Step 7: Handle Negative Values  
1. Filter out -1s from the Competitors column  
2. Filter out 0s from the Revenues column  
3. Remove -1s from the Industry column  

### Step 8: Clean Company Names  
1. Remove any extra characters or ratings after company names  

### Step 9: Copy Cleaning Steps as Proof  
1. Go to Home Menu → Click Advanced Editor  
2. Copy and save the code in your portfolio  



### Step 10: Reshape and Group Data  
#### Group by Role Type  
1. Duplicate the raw data → Rename it as "Sal By Role Type dup"  
2. Select only Role Type, Min Salary, and Max Salary columns  
3. Change Min and Max Salary type to currency  
4. Multiply values by 1000 (Numbers Column → Standard → Multiply → Type 1000)  
5. Group rows by Role Type and get the average for Min and Max Salary  

#### Group by Company Size  
1. Create a reference of raw data → Rename it as "Sal By Role Size ref"  
2. Select only Size, Min Salary, and Max Salary columns  
3. Change Min and Max Salary type to currency  
4. Multiply values by 1000  
5. Group rows by Size and get the average for Min and Max Salary  


### Step 11: Merge State Mapping  
1. Click Unclean DS Jobs  
2. Right-click in the Queries pane → New Query → Open Workbook State Mapping  
3. Select the columns and click OK  
4. Select Uncleaned DS Jobs query  
5. Choose the State Abbreviation column in both queries  
6. Click Merge → Click OK  
7. Rename the merged column as "State Full Name"  
8. Remove nulls and blanks  



### Step 12: Group by State  
1. Create a reference of raw data → Rename it as "Sal By State ref"  
2. Select only State Full Name, Min Salary, and Max Salary columns  
3. Change Min and Max Salary type to currency  
4. Multiply values by 1000  
5. Group rows by State Full Name and get the average for Min and Max Salary  



### Step 13: View Query Dependencies  
1. Go to View Menu → Click Dependencies  
2. Check if all queries are correctly linked

## Here are the screenshots showcasing the table transformation process
## Here's the screenshots before data cleaning.
![Before_Cleaning](https://github.com/user-attachments/assets/b7f418ea-8ea7-4bb6-ac53-c46bc280982a)
## Here's the screenshots when I started data cleaning.
![After_cleaning](https://github.com/user-attachments/assets/06883863-61df-4241-86d3-8697e6e94594)
## Here's the screenshots of Advanced Editor.
![Advanced Editor](https://github.com/user-attachments/assets/3c135208-da23-4ad6-9b4a-87ee403c0953)
## Here's the screenshot of Sal By Role type.
![salbyrole](https://github.com/user-attachments/assets/d1da5a5f-02f9-4dda-927f-a8ae96163577)
## Here's the screenshot of Sal By Size.
![sabyrolesize](https://github.com/user-attachments/assets/acd13c16-8729-41b0-8c70-9fe50694bcbc)

## Here's the screenshot of the States.
![states](https://github.com/user-attachments/assets/96867dff-802e-468d-9074-dfe4b9e68d73)

## Here's the screenshot of Sal By State.
![salbystates](https://github.com/user-attachments/assets/e96326b6-f94c-4578-bfbd-24151d66d88c)


## Here's the screenshot of the Query Dependencies.
![Query Dependencies](https://github.com/user-attachments/assets/2e9a9a30-b400-41fc-bce2-ee24fdfa8ebe)

## [BACK TO PORTFOLIO](https://tatinzzz.github.io/EDM-Portfolio/)
