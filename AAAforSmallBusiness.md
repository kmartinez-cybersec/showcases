<h1>Improving AAA For a Small Business</h1>
<h2>Details</h2>
An analysis of authentication, authorization, and accounting for a small business in a simulated scenario.

<h2>Scenario</h2>
A small business experienced a security incident in which an unauthorized payroll event was added. A log event is included, along with an employee directory.

![image](https://github.com/user-attachments/assets/c9f6e9bb-2a64-4a41-84bc-d1669fc1702c)

![image](https://github.com/user-attachments/assets/33b0b6f4-3403-4688-93c2-904f6f71c5ae)

<h2>Response</h2>

|Notes|Issues|Recommendations|
|---|---|---|
|* User is `Legal\Administrator` <br /> * Event occurred on `2023/03/18` at `8:29:57 AM` <br /> * Computer is `7TmhJaQCb` with IP address `152.207.255.255` <br /> <br /> Robert Taylor Junior seems to be a match for account type (Legal) and IP address (152.207.255.255); last login also corresponds with time of event occurring (8:29:57 am) | * All users have admin privileges; does not follow principle of least privilege <br /> * There seems to be one shared admin account for the entire Legal department, violating separation of duties <br /> * Robert Taylor Jr's access is still active despite his contract already ending | * Separate account should be made for each user (employee) <br /> * User accounts should only have authorization to make changes necessary and relevant to their job duties; a legal account should not have access to the payroll <br /> * User accounts should be deprovisioned after termination of employment | 
