<h1>Using Filters in SQL Queries</h1>

<h2>Description</h2>
Specific information about employees, their machines, and their respective departments must be retrieved in order to investigate security concerns and update certain computers. To filter the required records from the database, I must apply the appropriate filters to SQL queries.

<h2>Walkthrough</h2>
<h3>Retrieve after hours failed login attempts</h3>

In order to investigate a potential security incident occurring after business hours, I have to retrieve failed login attempts made after 18:00. This can be done using the comparison operators  > and = along with the logical operator AND in the following command:
```sql
SELECT *
FROM log_in_attempts
WHERE login_time > '18:00' AND success = 0;
```
This command returns the following:

![image](https://github.com/user-attachments/assets/5a524d67-132b-4579-b483-231d1c7e3b87)
The command had the desired output, as all login times have a success value of 0 and occur after 18:00.

<h3>Retrieve login attempts on specific dates</h3>
To investigate a suspicious event occurring on 2022-05-09, I want to review all login attempts made on the day of the event or the day before, 2022-05-08. The logical operator OR can be used for this in the following command:

```sql
SELECT * 
FROM log_in_attempts 
WHERE login_date = '2022-05-08' OR login_date = '2022-05-09';
```
Which returns:

![image](https://github.com/user-attachments/assets/bd2b2aed-3fd2-4806-afba-50b93a7c10ad)

All outputs have a login_date value of 2022-05-08 or 2022-05-09.

<h3>Retrieve login attempts outside of Mexico</h3>

The security team has determined that there have been suspicious login attempts, but they did not originate from Mexico. Due to the country column listing Mexico as both MEX and MEXICO, the LIKE operator must be used with a wildcard to match a pattern. The following command is used:

```sql
SELECT * 
FROM log_in_attempts 
WHERE NOT country LIKE 'MEX%';
```
This returns:

![image](https://github.com/user-attachments/assets/10e66426-c0fb-4d8f-9d9d-1813e48ba6e1)

There are no outputs with MEX or MEXICO in the country column.

<h3>Retrieve employees in Marketing</h3>

The security team wants to perform updates on all machines in the Marketing department for all offices in the East wing. There are two conditions that need to be filtered for, so the logical operator AND must be used. As there are multiple offices in the East wing, the LIKE operator must be used along with a wildcard. With these conditions in mind, the following command is used:

```sql
SELECT * 
FROM employees 
WHERE department = 'Marketing' AND office LIKE 'East%';
```
This command returns:

![image](https://github.com/user-attachments/assets/3c00c21d-71de-4af9-b8a5-de03c51073fc)

All results are in the Marketing department and have offices in the East wing of the facility. 

<h3>Retrieve employees in Finance or Sales</h3>
A different update must now be performed on the computers of all employees in the Finance or Sales department. To retrieve records for all employees in either of the departments, the OR operator must be used, resulting in the following command: 

```sql
SELECT * 
FROM employees 
WHERE department = 'Finance' OR department = 'Sales':
```
Resulting in:

![image](https://github.com/user-attachments/assets/ebccaed3-2783-4f01-9de6-5449f11c01cb)

All employees listed are in the Finance or Sales department.

<h3>Retrieve all employees not in IT</h3>
One more update needs to be made. This update was already made to the computers of all employees in the Information Technology department, so it does not need to be made to any computers in this department. The NOT operator must be used to filter out the Information Technology department, resulting in the command: 

```sql
SELECT * 
FROM employees 
WHERE NOT department = 'Information Technology';
```
Returning:

![image](https://github.com/user-attachments/assets/62d685ad-b75e-4d09-913b-45f52f6ec52b)

No results have Information Technology in the department column.

<h2>Summary</h2>
To complete the necessary tasks I had to use the AND, NOT, and OR operators in SQL queries to return the necessary records. Through my filtering the required information, my team is able to address security concerns and update any outdated machines. 
