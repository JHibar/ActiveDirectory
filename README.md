<h1>Active Directory Lab</h1>

<h2>Description</h2>
The project consists of a simple Active Directory Home Lab setup and configuration. It utilized protocols such as Active Directory Domain Services (AD DS), Dynamic Host Configuration Protocol (DHCP), Remote Access Service (RAS), and Domain Naming System (DNS). We will use 2 Virtual Machines (VM), Windows Server 2019 for our Domain Controller, and Windows 10 Pro as our client system.
<br />


<h2>Languages and Utilities Used</h2>

- <b>PowerShell</b>

<h2>Environments Used </h2>

- <b>Windows Server 2019</b>
- <b>Windows 10 Pro</b>
- <b>Oracle Virtual Box</b>

<h2>Walk-through:</h2>

Setup for the Windows Server 2019:<br/>
<br/>
2 network adapters (NAT and Internal)<br/>
At least 2048 (2 GB) base memory<br/>
The more processor core the better <br />
<br/>
<img src="https://github.com/user-attachments/assets/151e2041-240e-4979-8288-54ab8691473b" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />

Start the Windows Server and navigate to the network adapter options  <br/>
<br/>
<img src="https://github.com/user-attachments/assets/745397af-015f-4aec-8fb1-f756596b8ceb"/>
<br />
<br />
Enter the number of passes: <br/>
<img src="https://i.imgur.com/nCIbXbg.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Confirm your selection:  <br/>
<img src="https://i.imgur.com/cdFHBiU.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Wait for process to complete (may take some time):  <br/>
<img src="https://i.imgur.com/JL945Ga.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Sanitization complete:  <br/>
<img src="https://i.imgur.com/K71yaM2.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Observe the wiped disk:  <br/>
<img src="https://i.imgur.com/AeZkvFQ.png" height="80%" width="80%" alt="Disk Sanitization Steps"/>
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
