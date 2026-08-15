# Applying_SQL_Filters
Implementation of targeted SQL database queries and filtering scripts to parse massive corporate database transactional tables for security audit validation.

# Apply filters to SQL queries

## Project description

	Sql (Structured query language) is used for managing relational tables in databases for critical and not-critical information and access handling. In this project we will use various queries to practice retrieving data for different needs according to the incident team requirments.  
Here are two tables we will be working with.  
Table 1 . Employees  
![][image1]

Table 2 . log\_in\_attempts  
![][image2]

## Retrieve after hours failed login attempts

You recently discovered a potential security incident that occurred after business hours. To investigate this, you need to query the **log\_in\_attempts** table and review after hours login activity. Use filters in SQL to create a query that identifies all failed login attempts that occurred after 18:00. (The time of the login attempt is found in the **login\_time** column. The **success** column contains a value of **0** when a login attempt failed; you can use either a value of **0** or **FALSE** in your query to identify failed login attempts.) 

QUERY : SELECT \* FROM log\_in\_attempts WHERE login\_time \> ‘18:00’ AND success \= 0;

OUTPUT  
![][image3]  
\[The result contains all the data from all the columns where the login\_time outside of working hours and unsuccessful log attempts \]  
Here the conditions login\_time \> ‘18:00’ constraints the data of the column login\_time to be greater than ‘18:00’ (time).  
With AND key word the constraint is further extended to be an unsuccessful login attempt using success \= 0\.  
The AND keyword operates information to result after both the conditions are fulfilled and results in the data where both conditions are TRUE.

## Retrieve login attempts on specific dates

A suspicious event occurred on 2022-05-09. To investigate this event, you want to review all login attempts which occurred on this day and the day before. Use filters in SQL to create a query that identifies all login attempts that occurred on 2022-05-09 or 2022-05-08. (The date of the login attempt is found in the **login\_date** column.)   
QUERY & OUTPUT : ![][image4]

Here the conditions are login\_date \= ‘2022-05-09’ or login\_date \= ‘2022-05-08’,  
The OR keyword filters the data by either one condition is TRUE.  
Therefore the resulting table contains the complete data of login attempts in both dates.  
![][image5]

## Retrieve login attempts outside of Mexico

There’s been suspicious activity with login attempts, but the team has determined that this activity didn't originate in Mexico. Now, you need to investigate login attempts that occurred outside of Mexico. Use filters in SQL to create a query that identifies all login attempts that occurred outside of Mexico. (When referring to Mexico, the **country** column contains values of both **MEX** and **MEXICO**, and you need to use the **LIKE** keyword with **%** to make sure your query reflects this.) 

QUERY & OUTPUT :   
![][image6]![][image7]  
The keyword NOT is used to eliminate the certain condition in the output   
And the keyword LIKE with % is used to find the similar char in the column to particular condition where % represents the position of remaining chars.  
Here in the result we excluded all the data containing the country as MEX or MEXICO.

## Retrieve employees in Marketing

Your team wants to perform security updates on specific employee machines in the Marketing department. You’re responsible for getting information on these employee machines and will need to query the **employees** table. Use filters in SQL to create a query that identifies all employees in the Marketing department for all offices in the East building.

(The department of the employee is found in the **department** column, which contains values that include **Marketing**. The office is found in the office column. Some examples of values in this column are **East-170**, **East-320**, and **North-434**. You’ll need to use the **LIKE** keyword with **%** to filter for the East building.)

QUERY & OUTPUT :   
![][image8]  
Similar to previous practices, the AND and LIKE keyword is used to result in the required.  
The condition department \= ‘Marketing’ explains to only fetch data in the table where the department is Marketing.

## Retrieve employees in Finance or Sales

Your team now needs to perform a different security update on machines for employees in the Sales and Finance departments. Use filters in SQL to create a query that identifies all employees in the Sales or Finance departments. (The department of the employee is found in the **department** column, which contains values that include **Sales** and **Finance**.) 

QUERY & OUTPUT :   
![][image9]![][image10]  
Similar to previous practices we are fetching the data in the table where departments are Finance or Sales using OR keyword.

## Retrieve all employees not in IT

Your team needs to make one more update to employee machines. The employees who are in the Information Technology department already had this update, but employees in all other departments need it. Use filters in SQL to create a query which identifies all employees not in the IT department. (The department of the employee is found in the **department** column, which contains values that include **Information Technology**.) 

QUERY & OUTPUT :   
![][image11]![][image12]  
Here the NOT keyword is used to fetch the data in the table excluding the Information Technology department information.

## Summary

In Summary we have practiced different types of SQL queries including keyword NOT, LIKE, OR, AND and operators \>, \= for various purposes and to fetch different combinations of data as per requirements to the appropriate scenario.

This project helps in understanding the importance of SQL in real incidents and understanding .  
And queries in sql to fetch the required data for required scenarios.

[image1]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_151459_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-bo.jpeg

[image2]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_145339_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-bo.jpeg

[image3]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_145616_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-bo.jpeg

[image4]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_1508_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-boat.jpeg

[image5]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_145921_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-bo.jpeg

[image6]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_15158_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-boa.jpeg

[image7]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_1539_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-boat.jpeg

[image8]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_15523_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-boa.jpeg

[image9]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_15740_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-boa.jpeg

[image10]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_15716_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-boa.jpeg

[image11]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_15913_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-boa.jpeg

[image12]:https://raw.githubusercontent.com/LakshanRaghav/Applying_SQL_Filters/refs/heads/main/supporting_docs/Screenshot_8-8-2026_15922_kde424mkzlvwz7gt2sadjez5wqsekdgzd5rvjaxz34pd6edfwzyq.us-east1-b.resources.bumper-boa.jpeg
