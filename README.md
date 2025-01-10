<h1>Performing a Query with Splunk and Chronicle</h1>

<h2>Description</h2>
In this lab, we will perform a basic query in both Splunk and Chronicle. The purpose is to familiarize with both SIEM tool platforms and learn to navigate through the interfaces, as well as apply filters to narrow search results. <br/>
<br />
In Splunk, our task is to explore any failed SSH logins for the root account on the mail server, which could alert of suspicious activity. <br/>
<br />
In Chronicle, we will investigate a suspicious domain that was found in a phishing email to determine if it is malicious or not.


<h2>Languages and Utilities Used</h2>

- <b>Search Processing Language (SPL)</b>
- <b>YARA-L</b>

<h2>Environments Used </h2>

- <b>Splunk</b>
- <b>Google Chronicle</b>

<h2>Program Walk-Through:</h2>

<h3>Perform a Query in Splunk</h3>

<p align="center">
Splunk utilizes a search bar for querying data on the platform. We will begin by searching <em><strong>index="main"</strong></em>, which specifies a repository for data. This index is a single dataset containing events from an index named main. We also select "all time" from the time range dropdown to search for all events across all time: <br/>
<img src="https://i.imgur.com/9HGemGb.png" height="100%" width="100%" alt="Splunk Query"/>
<br />
<br />
We need to narrow the search results for events from the mail server, which be found under "SELECTED FIELDS". We will select the "host" as "mailsv". Note that doing so will also add it to the search bar:  <br/>
<img src="https://i.imgur.com/f3Xu0e0.png" height="100%" width="100%" alt="Splunk Query"/>
<br />
<br />
We will narrow the search further to locate any failed SSH logins for the root account. We can do so by adding "fail* root" in the search bar which will search for the keyword "fail" and any other variation of the word, and the keyword "root": <br/>
<img src="https://i.imgur.com/d581CwW.png" height="100%" width="100%" alt="Splunk Query"/>
</p>
<br />
<br />

<h3>Perform a Query in Chronicle</h3>

<p align="center">
We first start by typing the domain in question, "signin.office365x24.com" in the search bar:  <br/>
<img src="https://i.imgur.com/LT8bVSV.png" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
Here we can see what the overview page of the domain looks like, which includes information like the VirusTotal context, WHOIS, and sibling domains:  <br/>
<img src="https://i.imgur.com/o9RZMx6.png" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
By clicking on "Resolved IPs" we can see what IP address the domain maps to, which is "40.100.174.34:  <br/>
<img src="https://i.imgur.com/bdy2QTs.png" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
If we click on "VT Context", we can see that 11/94 security vendors flagged this domain as malicious:  <br/>
<img src="https://i.imgur.com/q3eAh5R.png" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
Now if we click on "Timeline" we can see details about the HTTP requests that were made to the domain, including "GET" and "POST" which requests and sends information to the domain. We can see that several assests sent both GET and POST requests:  <br/>
<img src="https://i.imgur.com/KQShbft.png" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
After collecting this information on the domain, we can conclude that it is suspicious and most likely malicious. Before ending the investigation, we also want to look at the IP address found under "Resolved IPs" to see if the "signin.office.365x24.com" domain uses another domain:  <br/>
<img src="https://i.imgur.com/0O0GhYg.png" height="100%" width="100%" alt="Chronicle Query"/>
</p>
<br />
<br />

