# Project 8 - Pentesting Live Targets

Time spent: **5.5** hours spent in total

> Objective: Identify vulnerabilities in three different versions of the Globitek website: blue, green, and red.

The six possible exploits are:
* Username Enumeration
* Insecure Direct Object Reference (IDOR)
* SQL Injection (SQLi)
* Cross-Site Scripting (XSS)
* Cross-Site Request Forgery (CSRF)
* Session Hijacking/Fixation

Each version of the site has been given two of the six vulnerabilities. (In other words, all six of the exploits should be assignable to one of the sites.)

## Blue

Vulnerability #1: SQL Injection, the developer forgot to sanitize the URL input for the salesperson ids and it was open to manipulation through the use of OR/AND queries.

Vulnerability #2: Session Hijacking/Fixation, implementation of a certified unique session_ID was never implemented to prevent hijacking.


## Green

Vulnerability #1: Username Enumeration, the developer seems to have checked the password after making sure the user account exists and then assigned a different class of "failed" instead of the usual "failure" if it fails at that stage.

Vulnerability #2: Cross-Site Scripting, the developer left out the filtering in both the name field and the comments field of the feedback to allow active javascript in both to run as soon as an admin opened up feedback.


## Red

Vulnerability #1: Insecure Direct Object References, the developer left the place holder for testing salesperson "Testy McTesterson" as well as a previously fired worker "Lazy Lazyman" available for public viewing even though the testing salesperson states it shouldn't be and the fired individual logically shouldn't be.

Vulnerability #2: Cross-Site Request Forgery


## Notes

I couldn't quite figure out number 5 correctly, but I figure it's the second Red site Vulnerability since it's my last unchecked vulnerability. I also wasted some time running sqlmap on the login pages figuring I was missing something over and over before I realized that SQL injection through URL is, indeed, a thing.
