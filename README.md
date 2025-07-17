# 🐶 NYC Dog Licensing Dashboard

## Project Overview

This project uses real dog licensing data from New York City to explore trends in pet ownership across ZIP codes, time, breed, and dog age. The goal is to identify patterns that can help city agencies or animal organizations plan more effective and better-targeted town halls for dog owners.  
The project includes data cleaning and feature engineering in Python, followed by interactive visualizations built in Tableau.

## Stakeholder Description

**Stakeholder:** New York City Director of Animal Services.

The goal is to help the shareholder connect with dog owners by hosting seasonal town halls, sharing resources, and educating the public about dog licensing and pet care.
So our team has focused on finding the lowest and highest rates at which dog licenses are issued throughout the boroughs of New York City, and the average age at which dog licenses are issued. 

## Core Business Question: 
> **Are there patterns in current dog licensing rates that help us plan and promote future town halls more effectively?**
The dashboard answers this question by identifying:
- Where dog licenses are concentrated (geographically)
- When licenses are issued most frequently (seasonally)
- The dog age distribution  

## Exploratory Data Analysis (EDA) in Python
**Tools Used:** `pandas`, `matplotlib`, `seaborn`, and `plotly`

1. **Data Cleaning**
   Our team started its data cleaning process by making sure each column was corrected format. This included:
   - Renaming the columns for easy data handling
   <img width="428" height="172" alt="Screenshot 2025-07-16 at 11 51 01 PM" src="https://github.com/user-attachments/assets/e3963b55-e645-4151-a992-03aca0304920" />

   - Removing rows with missing values (e.g., gender, breed, ZIP, date).
   -   We dropped 1810 rows in the `name column`, 21 rows in `Gender`, and 82 in `Licence expire date`. We dropped all these rows because they only represent 1% of all the data in our dataset
   - Checking the data type for each column in the dataset, and next changing the one in the wrong format.
     <img width="539" height="116" alt="Screenshot 2025-07-16 at 11 59 03 PM" src="https://github.com/user-attachments/assets/ab94f70f-1bfa-4cf4-a833-24928f1a4704" />

   - Matching NYC zip codes to their corresponding boroughs. Pin-pointing neighborhoods. This was done by creating a function. We first created a dictionary that defined the borough names with their corresponding zip codes. The function get_borough() takes in a zipcode as an argument and checks to see if that zipcode falls within the listed dictionary. If it does, then it returns the borough name. For example, any zipcode from 10001 - 10282 would be considered Manhattan, and so forth.
     <img width="633" height="434" alt="Screenshot 2025-07-17 at 12 01 55 AM" src="https://github.com/user-attachments/assets/c5f3b98c-63fa-4b07-98fb-cc10449ce89a" />

  2. **Feature Engineering**
     We created three new columns to help find more insights with the data.
     - `DogAgeAtLicense`: Calculated age based on birth year and license date.
     - `IssueMonth` and `IssueYear`: Extracted from license issue date.
       <img width="724" height="116" alt="Screenshot 2025-07-17 at 12 10 22 AM" src="https://github.com/user-attachments/assets/18141a48-e667-42bf-8c3e-b7d5b3dd2fb1" />

     - Filtered out unrealistic ages (<0 or >25). In this large dataset, we have bad data, like: Dogs that appear to be 30 years old, which is not realistic (the average dog lifespan is 10–15 years) So we removed rows where: The age is less than 0 → probably a mistake or The age is more than 25 → extremely rare or likely wrong. 
        <img width="586" height="33" alt="Screenshot 2025-07-17 at 12 16 47 AM" src="https://github.com/user-attachments/assets/c8d533cb-d550-4a9b-89c0-6382d1f88dca" />

  3. **Export**

     The final cleaned dataset is saved as `final_dataset.csv` for use in Tableau.

     <img width="384" height="33" alt="Screenshot 2025-07-17 at 12 23 40 AM" src="https://github.com/user-attachments/assets/295d0eae-6b37-4035-8248-a9e9719cc3be" />



  5. Tableau Workflow / Visualizations
     
     After importing the cleaned dataset in Tableau, our team was tasked with creating data visualizations with easier access to the information when it comes to              neighborhoods with the highest and lowest Dog licenses issued, and the average ages of dogs for which these licenses are issued, which can help create awareness and       contribute to public health safety. 
        <img width="1357" height="734" alt="image" src="https://github.com/user-attachments/assets/2099d6fd-293d-4cd5-8e69-7dc3dac72dd3" />


      Our dashboard allows users to:
     - Filter by borough and license issue year.
     - View boroughs with the highest and lowest dog license rates.
     - Analyze the average age of dogs at license issuance.
     This Dashboard helps stakeholders identify where outreach and town halls are most needed.

      Find the final interactive dashboard built in Tableau here: [Dashboard](https://public.tableau.com/app/profile/kevin.serrano6220/viz/MODproject_17526900544830/Dashboard1?publish=yes)

## Business Recommendations

Based on our findings, we propose the following:
- Focus town halls in ZIP codes with high licensing activity (e.g., 11211, 10025).
- Schedule outreach between **April and July**, when license rates are highest.
- Tailor content to **new dog owners and puppies**, since most dogs are under 3 years old.
- Consider breed popularity by neighborhood when planning event topics or services.

  These efforts support:
  - Stronger community relationships
  - Enhanced public safety
  - Improved animal care and control
  - Higher rates of responsible pet ownership citywide
 
## Project Reflection

**Most Important Insight**:
> Most licenses are issued in the spring and early summer, and a large number of them are for very young dogs. This suggests town halls should focus on new dog owner support and be held between **April and July**, in areas with high registration activity.
> Also, the dashboard reveals the average age of dogs at the time of licensing. Late licensing can lead to missed vaccinations, raising public health risks, particularly related to rabies, a disease that poses a danger to both pets and humans.

**Prioritizing Dashboard Features**
> Given time constraints, we prioritized visualizations that directly aligned with our business question, those that highlighted licensing rates across boroughs, and showcased dog age distribution. These visuals most effectively support our case for targeted town halls and public health campaigns.

**Repo Navigation**
```
├── data/
│   ├── raw/
│         └──NYC_Dog_Licensing_Dataset_20250713.csv
│   └── cleaned/
│        └── final_dataset.csv
│──  notebooks/
│        └── data_cleaning.ipynb
└── README.md

```
**People who collaborated in this project**
- Ibrahima Diallo: [LinkedIn](https://www.linkedin.com/in/ibranova/)
- Kevin Serrano Lopez: [LinkedIn](https://www.linkedin.com/in/kevin-serrano-lopez/)
- Itzel Sanchez: [LinkedIn](https://www.linkedin.com/in/itzel-sanchez-8932b6334/)






     







