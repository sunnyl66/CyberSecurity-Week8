# Project 8 - Pentesting Live Targets

Time spent: **1** hours spent in total

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

Vulnerability #1: SQL Injection (SQLi)  
Running ``` ' OR SLEEP(5)=0--' ``` as the ID will set blue link to sleep for 5 seconds.
<img src='https://i.imgur.com/m0by2tZ.gif' title='SQLi' width='' alt='SQLi' />

Vulnerability #2: Session Hijacking/Fixation  
Getting already logged in Session ID and using it as Session ID for a new browser that is not logged in worked on blue link.
<img src='https://i.imgur.com/glmQbCz.gif' title='Session Hijacking/Fixation' width='' alt='Session Hijacking/Fixation' />

## Green

Vulnerability #1: Username Enumeration  
On green link, you can tell if account exists or not. Class failure is bold and it means the account exists. Class failed is not bold and it means the account doesn't exist.
<img src='https://i.imgur.com/1FumsyS.gif' title='Username Enumeration' width='' alt='Username Enumeration' />

Vulnerability #2: Cross-Site Scripting (XSS)  
Posting ```<script>alert('Sunny found the XSS!');</script>``` as a feedback will give an XSS when the admin views the feedbacks:
<img src='https://i.imgur.com/uH39H0d.gif' title='XSS' width='' alt='XSS' />

## Red

Vulnerability #1: Insecure Direct Object Reference (IDOR)  
On red link, you can change ID # and see people you normally aren't allowed to see.
<img src='https://i.imgur.com/4VyhCtN.gif' title='IDOR' width='' alt='IDOR' />
Vulnerability #2: Cross-Site Request Forgery (CSRF)  
By running a HTML form, we can change values of stuff on red site without being admin. The HTML is in this repo.
<img src='https://i.imgur.com/rvhiUdL.gif' title='IDOR' width='' alt='IDOR' />

## Notes

Not that bad. Was pretty fun working on this. Only "hard" one was CSRF, I had to google up forms for HTML.
