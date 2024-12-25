# Splunk: Search Commands

<h2>Description</h2>
In this SIEM task, I explored more Splunk search commands to create tables, search useragent strings, use geostats and iplocation geolocate clientips. 


<h2>Languages and Utilities Used</h2>

- <b>linux CLI</b>

<h2>Environments Used </h2>

- <b>Splunk</b>
- <b>Unbuntu</b> 

<br />
<br />
Sorting http_smaple index by -req_time to display the most recent request time first.  

![1) sort in descending req_time](https://github.com/user-attachments/assets/71d476de-0c14-4c38-bcee-d901f748102e)

<br />
<br />
Piping stats count by clientip, sorting by reverse count, and displaying head 5 shows the top 5 client ips by count. 

![2) stats count a sort with head 5](https://github.com/user-attachments/assets/25d904c0-7e69-454e-a149-307d6d492663)

<br />
<br />  
Creating a table for time, clientip, method, uri, and useragent.

![3) building a table in splunk](https://github.com/user-attachments/assets/300fe94e-92c0-4b2e-9bff-69040b29c44b)

<br />
<br />
Building on the table, sortin for dedup useragent to get rid of duplicates and renaming useragent to "User Agent".

![4) dedup (uniq) for useragent and renaming useragent](https://github.com/user-attachments/assets/943137e9-7bbe-48fb-b697-ee18a288af8a)

<br />
<br />
Displaying the top 5 user agents.

![5) returning top 5 values for user agent](https://github.com/user-attachments/assets/1f9723bb-10d2-4a9a-866d-e92d32c68c81)

<br />
<br />
On the other hand, using rare with limit=5 will show the rares useragents in the index. 

![6) returning the top 5 rarest values for user agent](https://github.com/user-attachments/assets/e2d25138-ac85-4d8c-aeb9-912d247339fc)

<br />
<br />
Piping chart count by status and selecting visualization will display the http status codes in a abr chart format. 

![7) chart count by http status](https://github.com/user-attachments/assets/6815d69e-e522-4f44-a252-a60d886ba176)

<br />
<br />  
With the known clientip for the hydra attack and piping for timechart with a span of 1s count and selecting visualization will display the clientip activity over a timespan. 

![8) sorting by highest ip pipe timechart span 1s count to show ip activity](https://github.com/user-attachments/assets/f22dcd0a-df24-4550-a269-49b5d4466c50)

<br />
<br />
From the table, piping a serach for userganet strings with *Nmap* wildcard to produce 29 results. 

![9) searching for useragent nmap within a table](https://github.com/user-attachments/assets/c33c7297-1898-4734-8b02-86076c282155)

<br />
<br />
Using the iplocation for clinetip unlocks the city and Country Interesting Fields. 

![10) iplocation for clientip shows city and country](https://github.com/user-attachments/assets/595dba5a-af14-4896-9e7e-d37ac3010ed9)

<br />
<br />
Creating a table from iplocation including Country and City columns. 

![11) table including city and country](https://github.com/user-attachments/assets/aefa3ba8-88e4-4a37-b5c5-6e2facd39d2e)

<br />
<br />
Using geostats count by Country to show a world map of concentrated clientips indicating a brute force attack from Ukraine.

![12) geostats by country and visualize onto map](https://github.com/user-attachments/assets/7f651bdb-7410-436e-9996-79fdc0300702)

<br />
<br />
