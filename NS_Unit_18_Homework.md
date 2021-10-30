# Unit 18 Homework: Lets go Splunking!

## Vandalay Industries Monitoring Activity Instructions

## Step 1: The Need for Speed

Background: As the worldwide leader of importing and exporting, Vandalay Industries has been the target of many adversaries attempting to disrupt their online business. Recently, Vandaly has been experiencing DDOS attacks against their web servers.
Not only were web servers taken offline by a DDOS attack, but upload and download speed were also significantly impacted after the outage. Your networking team provided results of a network speed run around the time of the latest DDOS attack.
Task: Create a report to determine the impact that the DDOS attack had on download and upload speed. Additionally, create an additional field to calculate the ratio of the upload speed to the download speed.

Upload the following file of the system speeds around the time of the attack.

Speed Test File

Using the eval command, create a field called ratio that shows the ratio between the upload and download speeds.

Hint: The format for creating a ratio is: | eval new_field_name = 'fieldA'  / 'fieldB'

Create a report using the Splunk's table command to display the following fields in a statistics report:

_time
IP_ADDRESS
DOWNLOAD_MEGABITS
UPLOAD_MEGABITS
ratio

Hint: Use the following format when for the table command: | table fieldA  fieldB fieldC.
Answer the following questions:


**Based on the report created, what is the approximate date and time of the attack?**

*On 2020-02-23 from 14:30:00 to 22:30:00 Approximatly.

![Need-for-Speed-4A](./Images/Need-for-Speed-4A.png)

**How long did it take your systems to recover?**

*As per log the system start working normally on 2020-02-23 23:30:00

![Need-for-Speed-4B](./Images/Need-for-Speed-4B.png)

![Need-for-Speed-4B](./Images/Need-for-Speed-4B.png)

**Step 2: Are We Vulnerable?**

Background:  Due to the frequency of attacks, your manager needs to be sure that sensitive customer data on their servers is not vulnerable. Since Vandalay uses Nessus vulnerability scanners, you have pulled the last 24 hours of scans to see if there are any critical vulnerabilities.

For more information on Nessus, read the following link: https://www.tenable.com/products/nessus


Task: Create a report determining how many critical vulnerabilities exist on the customer data server. Then, build an alert to notify your team if a critical vulnerability reappears on this server.


Upload the following file from the Nessus vulnerability scan.

Nessus Scan Results

Create a report that shows the count of critical vulnerabilities from the customer database server.

The database server IP is 10.11.36.23.
The field that identifies the level of vulnerabilities is severity.

![Are-We-Vulnerable-2-2](./Images/Are-We-Vulnerable-2-2.png)

Build an alert that monitors every day to see if this server has any critical vulnerabilities. If a vulnerability exists, have an alert emailed to soc@vandalay.com.

![Alert-A](./Images/Alert-A.PNG)


![Alert-B](./Images/Alert-B.PNG)


![Alert-C](./Images/Alert-C.PNG)


Submit a screenshot of your report and a screenshot of proof that the alert has been created.

Step 3: Drawing the (base)line
Background:  A Vandaly server is also experiencing brute force attacks into their administrator account. Management would like you to set up monitoring to notify the SOC team if a brute force attack occurs again.
Task: Analyze administrator logs that document a brute force attack. Then, create a baseline of the ordinary amount of administrator bad logins and determine a threshold to indicate if a brute force attack is occurring.


Upload the administrator login logs.

Admin Logins

**When did the brute force attack occur?**

*A spike occurred at approximately between 9 A.M - 1 P.M on February 21, 2020.  This is indicated by a much higher count of activity compared to the other hours.

**Determine a baseline of normal activity and a threshold that would alert if a brute force attack is occurring.**

- There is no perfect answer to this: thresholds may be adjusted as the normal count of bad logins and count of attacks changes.
However, based on the normal average of bad logins vs. attacks, setting a threshold to fifty bad logins per hour would likely identify attacks and minimize false positives.

**Design an alert to check the threshold every hour and email the SOC team at SOC@vandalay.com if triggered.**

Submit the answers to the questions about the brute force timing, baseline and threshold. Additionally, provide a screenshot as proof that the alert has been created.

![Drawing-the-(base)line](./Images/Drawing-the-(base)line.png)

![Drawing-the-(base)line-3A](./Images/Drawing-the-(base)line-3A.png)

![Drawing-the-(base)line-3B](./Images/Drawing-the-(base)line-3B.png)

