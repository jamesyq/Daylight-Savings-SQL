When developing an SSIS package (SQL Server Integration Services) that would return tasks that took more than 30 minutes to complete,
I wanted to find a way to get around daylight savings with regards to the addition of one or two hours, depending on the time of year 
(we are based in Spain which is either UTC +1 OR +2). 
 
This is the SQL query that I used to get around the issue. I created variables for the specific daylight savings
dates for winter and summer where the day, month and time will remain the same but the year will change depending 
on the current year. If the current date falls within the summer period, the @Hours_toADD variable will have a value
of 2. If it falls within the winter period, it will have a value of 1. I then created a variable within the SSIS 
package in Visual Studio that would contain the resulting value of either 1 or 2. This would be applied to my 
SSIS expression to determine the correct time to add depending on daylight savings.
