# Pewlett-Hackard-Analysis

## Overview

With a large number of employees approaching retirement age at Pewlett Hackard, an exercise was undertaken to understand the current employee structure and determine the number of retiring employees per title. Subsequently, to plan for succession in light of the ‘silver tsunami’, those employees from the current pool were identified who are eligible to participate in a mentorship program.

## Results

A retirement titles table was created to hold all titles of current employees born between 1 January 1952 and 31 December 1955, which gave us 133,776 employees.

![image]( https://github.com/amberwnaushahi/Pewlett-Hackard-Analysis/blob/main/Tables/retirement_titles.png)

From the table above, we can see that several employees are appearing more than once as they held multiple titles (due to promotions) during their employment with PH.  Therefore, a unique titles table was created using a DISTINCT ON statement to eliminate multiple entries per employee. This gave us 90,398 unique employees who are expected to retire soon, representing over 30% of current workforce. 

![image]( https://github.com/amberwnaushahi/Pewlett-Hackard-Analysis/blob/main/Tables/unique_titles.png)

In order to see the number of retirement-age employees by most recent job title,  I used the COUNT() and GROUP BY functions. This revealed that about 64% of retiring employees were Senior Engineers or Senior Staff.  

![image](https://github.com/amberwnaushahi/Pewlett-Hackard-Analysis/blob/main/Tables/retiring_titles.png)

Once the retirement profile was identified, I undertook a mentorship eligibility analysis and created a table holding details of existing employees eligible for participation in a mentorship program. The eligiblity criteria was age, whereby employees born in 1965 could participate. This gave us 1,549 eligible employees, which is only 0.5% of current workforce. 

![image]( https://github.com/amberwnaushahi/Pewlett-Hackard-Analysis/blob/main/Tables/mentorship_eligibility.png)

## Summary

* Based on the analysis, we can see that 90,398 roles will need to be filled as existing employees retire. (Query: SELECT count(DISTINCT (emp_no)) FROM retirement_titles)

* It appears that only 1,940 employees in the current pool of employees are eligible to be mentored to take over the roles that are left over from retiring employees. (Query: SELECT COUNT(emp_no) FROM mentorship_eligibility)

* We can undertake additional analysis such as the departments that have the highest number of potential retirees to understand where mentorship efforts need to be focused on.

* Taking into consideration the low amount of employees who are eligible for mentorship, Pewlett Hackard will face a great deficit once a majority of eligible employees retire. In addition to the age criteria for mentorship, we can also undertake separate analysis using the number of years that an employee has been with the organization to assess if they can be mentored to take over positions being opened due to retirement. This may give the management at Pewlett Hackard a larger number of internal candidates for filling in roles.

