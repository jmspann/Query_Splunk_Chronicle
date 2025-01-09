<h1>Performing a Query with Splunk and Chronicle</h1>

<h2>Description</h2>
In this lab, we will perform a basic query in both Splunk and Chronicle. The purpose is to familiarize with both SIEM tool platforms and learn to navigate through the interfaces, as well as apply filters to narrow search results. <br/>
<br />
In Splunk, our task is to explore any failed SSH logins for the root account on the mail server, which could alert of suspicious activity. <br/>
<br />
In Chronicle,


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
:  <br/>
<img src="" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
:  <br/>
<img src="" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
:  <br/>
<img src="" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
:  <br/>
<img src="" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
:  <br/>
<img src="" height="100%" width="100%" alt="Chronicle Query"/>
<br />
<br />
:  <br/>
<img src="" height="100%" width="100%" alt="Chronicle Query"/>
</p>
<br />
<br />

