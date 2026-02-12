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
<img src="[https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640286/Screenshot_2025-04-12_124935_tu5tk2.png" height="80%" width="80%" alt="AD DS via VM](https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770861029/Screenshot_2026-02-05_222520_oqco3n.png)"/>
<br />
<br />
Selecting local machine as the source:  <br/>
<img src="[https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640217/Screenshot_2025-04-12_125309_xmgq1h.png" height="80%" width="80%" alt="AD DS via VM](https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770861214/Screenshot_2026-02-05_222540_zxgeiw.png)"/>
<br />
<br />
Choose the local event log collection as the data input: <br/>
<img src="[https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640217/Screenshot_2025-04-12_125621_qdobwe.png" height="80%" width="80%" alt="AD DS via VM](https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770861454/Screenshot_2026-02-08_113442_ngqcja.png)"/>
<br />
<br />
Use "*" to initiate a search for all events over time:  <br/>
<img src="[https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640218/Screenshot_2025-04-12_125806_jeyask.png" height="80%" width="80%" alt="AD DS via VM](https://res.cloudinary.com/dsz8pn2ym/image/upload/v1770861745/Screenshot_2026-02-08_162248_y9dgew.png)"/>
<br />
<br />
Configure IPV4 and DNS Properties For NIC 2 For Users To Gain Access Using Local Internet:  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640223/Screenshot_2025-04-12_133413_x11kjb.png" height="80%" width="80%" alt="AD DS via VM"/>
<br />
<br />
Utilize Server Manager To Configure Roles & Features  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640226/Screenshot_2025-04-12_133751_rlhzrv.png" height="80%" width="80%" alt="AD DS via VM"/>
<br />
<br />
Select Local/Host As Server Destination  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640226/Screenshot_2025-04-12_135033_e8yrbe.png" height="80%" width="80%" alt="AD DS via VM"/>
<br />
<br />
Install Features For AD and DS  <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640226/Screenshot_2025-04-12_135115_qu7zwx.png" height="80%" width="80%" alt="AD Ds via VM"/>  
<br />
<br />
Confirm AD DS has been added <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640227/Screenshot_2025-04-12_135253_z5fboa.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Post Deployment Required For AD DS <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640227/Screenshot_2025-04-12_135403_oeocjq.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Select Forest For Highest Level of Organization. Specify Domain To Be Accessed <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640231/Screenshot_2025-04-12_135442_mwjsnq.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Specify Domain Options and Password <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640231/Screenshot_2025-04-12_135503_abalgm.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Specify Path For Database <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640231/Screenshot_2025-04-12_135657_j6gbau.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Complete Installation <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640231/Screenshot_2025-04-12_135733_z7u4bn.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Restart and login with domain password that was created <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640232/Screenshot_2025-04-12_140007_rhunhk.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Under AD User and Computers, add an admin object <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640235/Screenshot_2025-04-12_141209_ijm0dn.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Assign admin's login credentials <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640236/Screenshot_2025-04-12_141248_prqpnx.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Add admin to domain and verify user is populated under admin object. <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640236/Screenshot_2025-04-12_141332_czywht.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Login with admin credentials set earlier <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640237/Screenshot_2025-04-12_140725_nx92it.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
As domain admin enable and install remote access and features to local network <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640243/Screenshot_2025-04-12_142614_qofqh2.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Enable and configure remote sever tools and DHCP <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640256/Screenshot_2025-04-12_150623_v9bppw.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Confirm DHCP tab populates local server and configurations <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640257/Screenshot_2025-04-12_151357_jh8zr1.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Add a new scope to IPv4 addresses
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640257/Screenshot_2025-04-12_151509_escsgf.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Specify scope range <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640260/Screenshot_2025-04-12_151744_gsowkx.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Configure lease for IP's if required <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640261/Screenshot_2025-04-12_151834_zxvujq.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Specify parent domain for users that will be using DNS name resolution <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640266/Screenshot_2025-04-12_152007_glzbcp.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Confirm successful configuration <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640266/Screenshot_2025-04-12_152052_eiwmwv.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Example folder housing powershell scripts as well as text list of users' names <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640266/Screenshot_2025-04-12_155349_dagysn.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Run powershell utility <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640266/Screenshot_2025-04-12_160006_tejtrk.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Input script in powershell to create users from text list in a specific format to OU of users <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640269/Screenshot_2025-04-12_160123_guy1y4.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Example of texts containing user names to be pulled <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640272/Screenshot_2025-04-12_161119_uonicx.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Example of a script error that did not have the correct file path to be pulled from <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640274/Screenshot_2025-04-12_162330_tumrck.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Corrected file path for script to pull from. Verify users have been populated <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640275/Screenshot_2025-04-12_162725_nmy5bc.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Utilizing Oracle again, create a VM (Windows 10) as an example of a new user to join company domain <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640278/Screenshot_2025-04-12_165210_w7qsf2.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
With both vm's running, you can confirm internet connection configured for the new user through the local server <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640278/Screenshot_2025-04-12_165210_w7qsf2.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Use an account with permissions to assign user to domain <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640279/Screenshot_2025-04-12_190110_rucnbb.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
On DC vm, in AD settings, confirm new computer has populated in the computers tab <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640279/Screenshot_2025-04-12_191104_aqibv1.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
You can also confirm lease has began, if one was set earlier in the process <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640279/Screenshot_2025-04-12_190559_mmqj8p.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640287/Screenshot_2025-04-12_191246_gnfgra.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Back to example list of user that were added through the powershell script <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640280/Screenshot_2025-04-12_191229_mteovh.png" height="80%" width="80%" alt="AD DS via VM"/>  
<br />
<br />
Verify users can login using password set for all users earlier as well as username format <br/>
<img src="https://res.cloudinary.com/dsz8pn2ym/image/upload/v1744640287/Screenshot_2025-04-12_191246_gnfgra.png" height="80%" width="80%" alt="AD DS via VM"/>  
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
