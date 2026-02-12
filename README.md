<h1>Splunk Lab 1 - Data Input & Dashboards</h1>


<h2>Description</h2>
Configured a Splunk Enterprise lab to ingest Windows Security Event Logs from the local host using the Splunk Universal Forwarder. Collected and indexed local Security logs, then developed SPL queries to extract and analyze high-risk activity, specifically Event Code 1102 (Audit Log Cleared). Filtered events by host, EventCode=1102, and relevant fields to identify the associated user account, system name, and timestamp. Created simple SPL table visualizations (e.g., table _time, host, user, EventCode) to present structured findings for SOC-style monitoring and reporting. Validated detection logic by generating test events locally and documenting results to simulate incident triage workflows.
<br />


<h2>Utilities Used</h2>

- <b>Splunk Enterprise</b> 
- <b>Local Host</b>
- <b>Windows Event Viewer</b>



<h2>Environments Used </h2>

- <b>Windows 10</b>
- <b>Windows Event Log</b>

<h2>Lab walk-through:</h2>

<p align="center">
Launch the data input session: <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770861029/Screenshot_2026-02-05_222520_oqco3n.png"/>
<br />
<br />
Selecting local machine as the source:  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770861214/Screenshot_2026-02-05_222540_zxgeiw.png"/>
<br />
<br />
Choose the local event log collection as the data input: <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770861454/Screenshot_2026-02-08_113442_ngqcja.png"/>
<br />
<br />
Use "*" to initiate a search for all events over time:  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/Screenshot_2026-02-08_162248_y9dgew.png"/>
<br />
<br />
Open Event Viewer in Windows:  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770862805/Screenshot_2026-02-08_162358_c5z5ox.png"/>
<br />
<br />
Select "Security" from "Windows Logs" and clear logs:  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770862917/Screenshot_2026-02-08_162617_vc9td7.png"/>
<br />
<br />
Return to Splunk and search for "EventCode:1102", which is the Audit Log Clear event. That may be something that to question if repeated a certain amount of time over a period of time:  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770863434/Screenshot_2026-02-08_162911_yphesj.png"/>
<br />
<br />
Under Search & Reporting create a table view of the data:  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770863518/Screenshot_2026-02-08_163012_e0xrhw.png"/>  
<br />
<br />
Under dashboards create a new dashboard: <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770863672/Screenshot_2026-02-08_163027_fpzbgj.png"/>  
<br />
<br />
Under settings you cna add tabs to the table: <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770864498/Screenshot_2026-02-08_163012_wq2sbg.png"/>  
<br />
<br />
SPL query within pulled data can assist with looking further into data: <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770864938/Screenshot_2026-02-08_164149_epjwtq.png"/>  
<br />
<br />
exporting logs under the "Actions" tab utilizing JSON format, which is used on many platforms: <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770865063/Screenshot_2026-02-08_164230_aqmd2j.png"/>  
<br />
<br />

</p>

<!--
 ```diff
- text in red
+ text in green
! text in orange
# text in gray
@@ text in purple (and bold)@@
```
--!>
