# panalyt-data-interview

# Overall Steps:

  1.Develop the SQL query to answer the business question.
  
  2.Create a docker image that does the following:
  
    A.Starts PostgreSQL / MySQL
  
    B.Initializes tables based on the files mounted in /opt/data/
  
  3.Runs and prints out the result of the SQL query stored in /opt/sql/report.sql



# SQL Task:

Swan.com is a recruitment agency that is interested in figuring out key recruitment seasons for new candidates. At Swan, any month that has upwards of 1000 applications is considered a succesful one. Furthermore, if 3 or more consecutive months are succesful, they identify these consecutive months as a succesful 'season' of applications. 
Recently, you're tasked with finding out all the succesful seasons of applications that swan has had over the last few years. You are provided with their ATS data: https://drive.google.com/file/d/15c2x3YwI6uBRoungWZqUAE9k5RUTEj4E/

The provided link contains a csv file with the following schema:

__applications__:

````
+------------+-------+----------+-------------+
| appliedAt  | jobId | status   | candidateId |
+------------+-------+----------+-------------+
| 2021-01-01 | J001  | ACCEPTED | C001        |
| 2021-01-04 | J002  | REJECTED | C002        |
| 2021-01-03 | J003  | PENDING  | C003        |
````

Write a SQL query that provides the following output:

__result__:
````
+------------+-------------+
| month      | applications|
+------------+-------------+
| 2021-01-31 | 1500        |
| 2021-02-28 | 2000        |
| 2021-03-31 | 4000        |
| 2021-06-30 | 2500        |
| 2021-07-31 | 3000        |
| 2021-08-31 | 4950        |
| 2021-09-30 | 1000        |
+------------+-------------+
````
This result should contain all their successful seasons where each successful season consists of at least 3 or more consective months where the total number of applications per job per canndidate is at least 1000. In the example above we have two seasons.
