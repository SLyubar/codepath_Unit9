# Project 8 - Pentesting Live Targets

Time spent: **5** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:

* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each color is vulnerable to only 2 of the 6 possible exploits. First discover which color has the specific vulnerability, then write a short description of how to exploit it, and finally demonstrate it using screenshots compiled into a GIF.

## Blue

Vulnerability #1: SQL Injection

Description:
An unauthenticated website visitor can manipulate the query parameters of the URL to inject a SQL query. The steps are going on the website and clicking on Salesperson. Next, click on any one of the listed salespeople that have a hyperlink over their name. You will notice that you are redirected to a page with details about the employee and the URL will add an ID query parameter and assign it equal to a number. If you change the number to an apostrophe, you will successfully escape out of the SQL query and can inject custom queries.

<img src="https://github.com/SLyubar/codepath_Unit9/blob/main/blue-vuln1.gif">

## Green

Vulnerability #1: Cross-Site Scripting

Description:
The contact form on this website does not santize the inputs. Therefore, an unauthenticated user can submit HTML and Javascript into the body of the form. Once an authenticated user of the website checks the feedback forms, they will be greeted by a cross-site scripting alert.

<img src="https://github.com/SLyubar/codepath_Unit9/blob/main/green-vuln1.gif">


## Red

Vulnerability #1: Insecure Direct Object Reference

Description:
An unautehnticated website visitor can manipulate the query parameters of the URL to view details about employees that should not be public. This is very similar to the SQL injection vulnerability on the blue website. The steps are going on the website and clicking on Salesperson. Next, click on any one of the listed salespeople that have a hyperlink over their name. You will notice that you are redirected to a page with details about the employee and the URL will add an ID query parameter and assign it equal to a number. These numbers do not go any higher than nine if you click on the hyperlinks as you are supposed to do. However, if you change the number to a 10 or 11, you will successfully view the details of a new employee that has not started yet or a terminated employee.

<img src="https://github.com/SLyubar/codepath_Unit9/blob/main/red-vuln1.gif">


## Notes

The SQL injection and IDOR took some trial and error. I was unable to get the SQL injection to return data that it should not show publicly. I also could not find the additional three vulnerabilities.
