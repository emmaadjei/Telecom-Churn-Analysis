# Telecom Churn Analysis

## Table of Contents
- [Project Overview](#project-overview)
- [Data Sources](#data-sources)
- [Tools](#tools)
- [Data Preparation](#data-preparation)
- [Exploratory Data Analysis](#exploratory-data-analysis)
- [Data Analysis](#data-analysis)
- [Results and Findings](#results-and-findings)
-  [Recommendations](#recommendations)
-   [Credits](#credits)
-   [References](#references)

### Project Overview
This report provides a deep dive into key customer metrics, revenue trends, and churn factors, based on an analysis of a hypothetical telecom dataset. The findings offer valuable insights to help the company anticipate churn risks and implement data-driven retention strategies, ensuring sustained growth and customer loyalty.

![churn](https://github.com/user-attachments/assets/7f2eb561-4c0d-441c-90d9-5535687c5b34)

 
### Data Sources

The dataset for the analysis can be obtatined in the link below 

[Get data set here](https://selar.co/m/mk-data-consultz1)

### Tools
-  Power BI:
    -  Data Cleaning, Data Analysis, Data Visualization
    -   [Download Power BI here](https//microsoft.com)

### Data Preparation
Below are my key steps during data preparation:
-  Loaded data into Power Query 
-  Cleaned and formatted the data
    -   promoted headers, changed data type, replaced values, filed down,

        removed columns, removed duplicates, added conditional column

### Exploratory Data Analysis
The analysis of the data was guided by the following objectives:

- What are the demographic characteristics (age, gender, tenure) and engagement patterns of our customer base?
  
- How do different revenue streams contribute to overall financial performance, and what factors influence monthly revenue changes?
  
- What are the primary reasons for customer churn, and how does it impact the company?

### Data Analysis
Below are some of the Data Analytics Expressions (DAX) featured in the project:
-	Using ```CALCULATE``` function:
  
Active Customers = ```CALCULATE([Total Customers],telecom_customer_churn[Customer Status]IN{"Stayed","joined"})```

Churned Customers = ```CALCULATE([Total Customers],telecom_customer_churn[Customer Status]="Churned")```

Churned Customers Revenue Loss = ```CALCULATE(SUM(telecom_customer_churn[Total Revenue]),telecom_customer_churn[Customer Status]="Churned")```

Males = ```CALCULATE([Total Customers],telecom_customer_churn[Gender]="Male")```

Females = ```CALCULATE([Total Customers],telecom_customer_churn[Gender]="Female")```




-	Using Aggregates (```SUM, AVERAGE, COUNT, DIVIDE```)  functions:
  
 Total Revenue = ```SUM(telecom_customer_churn[Total Revenue])```
 
Average Age = ```AVERAGE(telecom_customer_churn[Age])```

Total Customers = ```COUNT(telecom_customer_churn[Customer ID])```

Customer Churn Rate = ```DIVIDE([Churned],[Total Customers],0)```

Churned Customer Revenue Loss % = ```DIVIDE([Churned Customers Revenue Loss],[Total Revenue],0)```




-	Created a Parameter:

Parameter = ```{("Active Customers", NAMEOF('All Measures'[Active]), 0),("Churned Customers", NAMEOF('All Measures'[Churned]), 1),("Females", NAMEOF('All Measures'[Females]), 2),("Males", NAMEOF('All Measures'[Males]), 3)}```
    
### Results and Findings
The analysis results are summarized as follows:

-  Customer Engagement Patterns:
The telecom company serves 7,043 customers (50.5% male, 49.5% female). Of 5,174 active customers, 51% prefer Fiber Optic internet, 33% DSL, and 16% Cable. Contract choices: 38% month-to-month, 35% two-year, 27% one-year. Most popular services: Unlimited Data (86%) and Phone Service (90%).

-  Revenue and Financials:
The company earned $21.37M last year. Revenue sources: Long Distance Charges (LDC) $5.28M, Extra Data Charges $48.32K, avg. monthly data usage 185K GB, and online services (e.g., streaming).

-  Churn Analysis:
The company lost 1,869 customers, with a churn rate of 26.54%, leading to an estimated revenue loss of $3.68M. Dropout reasons include better devices, competitor offers, customer service attitude, and network reliability.

### Recommendations
From the insights derived, the following actions are recommended:

- Address Service and Product Dissatisfaction
Invest in network infrastructure improvements to enhance reliability and speed.
Conduct customer satisfaction surveys to understand pain points and implement solutions.

- Competitive Pricing and Promotions
Implement targeted promotions to counter competitors’ offers.
Provide exclusive data plans, discounts, and loyalty benefits. Enhance Customer Service & Engagement

- Improve customer support training to reduce negative interactions.
Deploy AI-powered customer service bots to provide instant assistance and prevent frustration.  

- Improve Customer Retention Strategies
Develop personalized retention programs targeting Millennials and Gen X customers
Offer discounts and incentives for long-term contracts to reduce churn from month-to-month users.

### Credits
##### Team Members
- [Daniel Cobbinah Afful](https://www.linkedin.com/in/cobbinah-afful)
- [Christabel Ogbemi](https://www.linkedin.com/in/christabel-ogbemi)
- [Deke Essenam Benedicta](https://www.linkedin.com/in/eseenamdeke)
- [Emmanuel Justin Koomson](https://www.linkedin.com/in/emmanuelkoomsonj)
- [Emmanuel Adjei](https://www.linkedin.com/in/emma-adjei)

### References
- Data Analysis with Power BI on DataCamp
   -    [DataCamp](https//Datacamp.com)
