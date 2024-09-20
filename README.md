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
<img src="https://github.com/user-attachments/assets/151e2041-240e-4979-8288-54ab8691473b" width="80%" alt="Disk Sanitization Steps"/>
<br />
<br />
Start the Windows Server and navigate to the network adapter options, here I would recommend renaming the two different adapters so you know which is NAT and which one is the internal network.  <br/>
<img src="https://github.com/user-attachments/assets/745397af-015f-4aec-8fb1-f756596b8ceb"/>
<br />
<br />
Right-click on the internal network, and click properties. Then check the box for "Use the following IP address:" and enter in your desired IP address for your DC as well as the subnet mask (I am using 172.16.0.1 with a subnet mask of 255.255.255.0). The preferred DNS server can also be the same IP address or 127.0.0.1 as a default.
<img src="https://github.com/user-attachments/assets/8f7cb2ee-938a-42d4-91a4-e2a635c39259"/>
<br />
<br />
Now we will get AD DS up and running, open up the Server Manager click on "Add roles and features".
<img src="https://github.com/user-attachments/assets/b1d15e20-eb80-45f6-bc40-cf0aa5ad1dbe"/>
<br />
<br />
On the pop-up, we will click "Next >" until we get to the Server Selection, there should just be the one choice for the server, make sure it is highlighted and click "Next >"
<img src="https://github.com/user-attachments/assets/93db3679-fc88-4f82-8455-8bddf811b77d"/>
<br />
<br />
Click on the check box for "Active Directory Domain Service"
<img src="https://github.com/user-attachments/assets/45bb6e9a-1b1b-4a1f-b992-9df9fe3f275d"/>
<br />
<br />
On the pop-up window, just click "Add Features"
<img src="https://github.com/user-attachments/assets/fd10ce88-8304-4705-9b9a-3820ef52991b"/>
<br />
<br />
Click "Next >" until you get to the last page, and click "Install"
<img src="https://github.com/user-attachments/assets/aac4a869-bb7f-4cf2-bee1-52ac8f939a0d"/>
<br />
<br />
Once that completes the install close that window, then go up to the flag in the top right and click on "Promote this server to a domain controller"
<img src="https://github.com/user-attachments/assets/9ce66490-45dc-44d2-9234-8cdb685a3bf4"/>
<br />
<br />
On the pop-up window, we will click on "Add a new forest" and enter in your desired root domain name (I am just using mydomain.com to keep it simple). Then click "Next >"
<img src="https://github.com/user-attachments/assets/c3ff4a78-57be-4b62-a13c-acb1c7a1666e"/>
<br />
<br />
Enter in a password for DSRM and click "Next >"
<img src="https://github.com/user-attachments/assets/4e3fe0e0-99b1-47cd-ad61-aeff114851c0"/>
<br />
<br />
Click "Next >"
<img src="https://github.com/user-attachments/assets/1e8765f3-bca9-4a57-af5c-4f935d940874"/>
<br />
<br />
This should auto-populate with the domain name, click "Next >"
<img src="https://github.com/user-attachments/assets/f454fff6-ac1a-4cd8-9120-bd47158296f1"/>
<br />
<br />
Click "Next >" until you get to the Prerequisites Check and click "Install"
<img src="https://github.com/user-attachments/assets/daf5885d-248a-407c-8e77-dc5234dad398"/>
<br />
<br />
The previous step should have restarted the machine automatically
<img src="https://github.com/user-attachments/assets/aa0d4900-8250-4131-9e15-62cd42d15aa3"/>
<br />
<br />
Now you can see that we have our domain root "MYDOMAIN" <br />
Log back in with your credentials
<img src="https://github.com/user-attachments/assets/3a126dad-714a-4bc9-812c-c2dc58e12e4a"/>
<br />
<br />
Once back in, open the Start Menu and click on "Active Directory Users and Computers"
<img src="https://github.com/user-attachments/assets/edf4223a-8768-4bd5-9c7b-78a75da12709"/>
<br />
<br />
On the new window, right-click on "mydomain.com", go to "New" and click on "Organizational Unit"
<img src="https://github.com/user-attachments/assets/8f623d36-c33e-40c5-8a8d-9318445258a1"/>
<br />
<br />
Now we will create an admin organizational unit to put ourselves in (I named it _ADMINS), click on "OK"
<img src="https://github.com/user-attachments/assets/3bde5067-a8ab-459d-81ad-481036e51717"/>
<br />
<br />
Now right-click on the _ADMINS folder, go to "New" and then click on "User"
<img src="https://github.com/user-attachments/assets/aa2efefd-c9f6-40f4-be26-96c6fc16c94a"/>
<br />
<br />
Now create your admin account, I am using myself in this demonstration, for the "User logon name" I chose "a-jhibar" to distinguish it as an admin account. Click on "Next >" once completed
<img src="https://github.com/user-attachments/assets/811c3e34-26cd-457e-bfb8-f8407cc36e84"/>
<br />
<br />
Create a password for this admin account, and check the boxes associated with your organization's password criteria (I am choosing to check "Password never expires" because it is a home lab. Click "Next >"
<img src="https://github.com/user-attachments/assets/3808ba83-262d-4517-810a-8fe175f47bd8"/>
<br />
<br />
Check that everything is correct and click "Finish"
<img src="https://github.com/user-attachments/assets/9932bc5a-bfa8-4d1e-a707-f227143f3e60"/>
<br />
<br />
Now we will make this user an admin, right-click on the new user and click "Properties"
<img src="https://github.com/user-attachments/assets/3f9b60be-104b-41d5-8d1b-fdaa2f983a98"/>
<br />
<br />
Click on the "Member Of" tab, and click "Add..."
<img src="https://github.com/user-attachments/assets/79a742f9-1d17-4ce0-b3cd-9e892cebee51"/>
<br />
<br />
In the bottom field, enter "domain admins" and click on "Check Names"
<img src="https://github.com/user-attachments/assets/7d7c964c-85ab-4a22-b8b4-ae8cf01c7940"/>
<br />
<br />
It should auto-correct the name and underline it to show that it is a valid object name. Click "Next>"
<img src="https://github.com/user-attachments/assets/5e49c4f3-18a8-4bf2-944e-5c261462cec2"/>
<br />
<br />
Now the user should be a part of both Domain Users and Domain Admins. Click "Apply" and then "OK"
<img src="https://github.com/user-attachments/assets/25bc041d-7d4a-4af8-9286-705fc1951f1c"/>
<br />
<br />
Go ahead and log out, now click on "Other user" and sign in with your new admin user account
<img src="https://github.com/user-attachments/assets/b3729629-989f-4be1-ae38-c70b95f401a1"/>
<br />
<br />
Now we will add and configure our RAS. Go back to the Server Manager Dashboard and click on "Add roles and features". Click "Next >" until you get to "Select server roles" and check the box for "Remote Access"
<img src="https://github.com/user-attachments/assets/26e1ed42-c3f3-46be-a61e-a7a571fdf9fd"/>
<br />
<br />
Click on "Add Features" and then "Next >"
<img src="https://github.com/user-attachments/assets/a50a337b-7f1e-4af9-802b-5e768250c91b"/>
<br />
<br />
Check the box for "Routing" and click "Next >"
<img src="https://github.com/user-attachments/assets/7baf404a-5c89-49be-ab7b-f4699eafc549"/>
<br />
<br />
Click "Next >" until the last page, and click "Install"
<img src="https://github.com/user-attachments/assets/e56a8981-5b59-4eaa-8dd0-d2fa7f64fd82"/>
<br />
<br />
Once the feature finished installation, click "Close"
<img src="https://github.com/user-attachments/assets/ccb8dfbb-748d-4c96-a5a8-851fcf711327"/>
<br />
<br />
Click on the "Tools" drop-down and then click "Routing and Remote Access"
<img src="https://github.com/user-attachments/assets/3f10dfb1-d767-4855-b740-414c7c207334"/>
<br />
<br />
On the pop-up window right-click on your Domain Controller and click "Configure and Enable Routing and Remote Access"
<img src="https://github.com/user-attachments/assets/3910b070-e731-4ed3-ada0-1bf1233abbb0"/>
<br />
<br />
Check the box for "Network address translation (NAT) and click "Next >"
<img src="https://github.com/user-attachments/assets/29b2b312-e64a-4118-bbd3-060833e1f490"/>
<br />
<br />
Highlight the NAT adapter for the public interface (should be something like 10.0.2.15), click "Next >"
<img src="https://github.com/user-attachments/assets/886e2a47-5f39-43ea-9c35-a8bfa9324988"/>
<br />
<br />
Click "Finish"
<img src="https://github.com/user-attachments/assets/0d88422a-406b-422a-9909-8ef98f58f6c7"/>
<br />
<br />
Now we can see that DC has a green arrow indicating that it is configured correctly. Go ahead and close out this window
<img src="https://github.com/user-attachments/assets/f13da5f2-7023-4d77-ba3d-e0d4194ec2b4"/>
<br />
<br />

<img src="https://github.com/user-attachments/assets/f13da5f2-7023-4d77-ba3d-e0d4194ec2b4"/>
<br />
<br />
Now we will set up DHCP. Go back to the Dashboard and click on "Add roles and features". Click "Next >" until we get to the "Server Selection" page, we can now see that the name of our server is DC.mydomain.com showing that we are configured correctly up to this point. Click "Next >"
<img src="https://github.com/user-attachments/assets/d439e4b5-3f6b-4fbc-9311-b85b69d0285e"/>
<br />
<br />
Check the box for "DHCP Server"
<img src="https://github.com/user-attachments/assets/1d7b6838-59df-4b94-89cb-c7650f11e051"/>
<br />
<br />
Click "Add Features" and then click "Next >"
<img src="https://github.com/user-attachments/assets/e664681e-5b6b-4a2a-8cb0-868e53aa3b92"/>
<br />
<br />
Click "Next >" until the final page and click "Install"
<img src="https://github.com/user-attachments/assets/b876cdb9-12a5-48f8-84f8-e046aa162388"/>
<br />
<br />
Once the feature has completed installation, close out of the window
<img src="https://github.com/user-attachments/assets/5014c314-421d-49a4-acf5-0eb001c108cc"/>
<br />
<br />
Click on the "Tools" drop-down and click on "DHCP"
<img src="https://github.com/user-attachments/assets/705214e6-df88-447c-bb7a-52c84f1be333"/>
<br />
<br />
Now we will set up our scope for DHCP. Click on the server and right-click on IPv4 then click on "New Scope..."
<img src="https://github.com/user-attachments/assets/4e6236cb-8da7-4d8e-8f20-3a906f31d428"/>
<br />
<br />
Set the name to what you prefer (I like to do the range of my DHCP addresses: 172.16.0.100-200), and click "Next >"
<img src="https://github.com/user-attachments/assets/c0b30df4-5e5c-478e-b4d8-7242e6b21d21"/>
<br />
<br />
Now set your "Start IP address" and "End IP address" as well as the length to achieve the desired subnet mask (Start: 172.16.0.100 | End: 172.16.0.200 | Length: 24| Subnet mask: 255.255.255.0). Click "Next >"
<img src="https://github.com/user-attachments/assets/debaa7ae-6811-4220-983c-a6642db1c55a"/>
<br />
<br />
Add exclusion and delay if desired, I am not for this particular network. Click "Next >"
<img src="https://github.com/user-attachments/assets/fcc87d5c-6d11-4584-a022-16f8d9303fa1"/>
<br />
<br />
Now we set our Lease Duration, depending on the scope of the network you might change this to something else (ie. 2 hours for a coffee shop public network so that the DHCP leases are not being taken up by people not there). Click "Next >"
<img src="https://github.com/user-attachments/assets/85dfaa67-11cd-4e0b-b0f5-a9fe0c3126d0"/>
<br />
<br />
Now make sure that the "Yes, I want to configure the DHCP options for the scope now" and click "Next >"
<img src="https://github.com/user-attachments/assets/37ccf0c5-eb70-49aa-9fe5-0c59dd136396"/>
<br />
<br />
For the router set it as the internal network IP address that you changed previously, this is what clients will connect to in order to be able to access the internet (you may have to add it). Make sure it is highlighted and click "Next >"
<img src="https://github.com/user-attachments/assets/7ebf5bc4-ff4b-4cce-b29c-da10974471d3"/>
<br />
<br />
For DNS Servers you may need to add the correct IP address but we should choose the same as the router IP address. Click "Next >"
<img src="https://github.com/user-attachments/assets/849dc4fd-66bf-4394-b977-e698de4625d0"/>
<br />
<br />
WINS Server is not necessary, so here just click "Next >"
<img src="https://github.com/user-attachments/assets/e3c3f9e8-34c5-44d5-8068-dbb3e6e29474"/>
<br />
<br />
Click on "Yes, I want to activate the scope now", and click "Next >"
<img src="https://github.com/user-attachments/assets/09b6b316-680e-459f-8aa4-1fd06a764b65"/>
<br />
<br />
Click "Finish"
<img src="https://github.com/user-attachments/assets/ba8fe2dc-96c7-40d9-b0b4-729ca7e434ba"/>
<br />
<br />
Now right-click on the server again and click "Authorize"
<img src="https://github.com/user-attachments/assets/d79f84f5-2755-4434-8117-946528773bb7"/>
<br />
<br />
Right-click on the server again and click "Refresh"
<img src="https://github.com/user-attachments/assets/00c6ff51-d068-4e9b-9954-6d468ef56cc7"/>
<br />
<br />
Now we can see that IPv4 has our scope under it and it is showing up as green indicating proper configuration
<img src="https://github.com/user-attachments/assets/41b883ae-ecf4-4e55-9982-2e5140587ee4"/>
<br />
<br />
Now we will add 1k users to our server to make it more realistic. Open up Powershell ISE as administrator
<img src="https://github.com/user-attachments/assets/7a63c990-f0c3-4884-8dc8-7efdf88912af"/>
<br />
<br />
Download the PowerShell script HERE https://github.com/joshmadakor/AD_PS/archive/master.zip <br />
Open the "1_CREATE_USERS" script in your Powershell window <br />
In the bottom field, we will type "Set-ExecutionPolicy Unrestricted" so that we are able to execute the script, click "Yes to all"
<img src="https://github.com/user-attachments/assets/b521dfdd-4fd3-4721-a983-9cfc1e5fcbe9"/>
<br />
<br />

<img src="https://github.com/user-attachments/assets/f13da5f2-7023-4d77-ba3d-e0d4194ec2b4"/>
<br />
<br />

<img src="https://github.com/user-attachments/assets/f13da5f2-7023-4d77-ba3d-e0d4194ec2b4"/>
<br />
<br />

<img src="https://github.com/user-attachments/assets/f13da5f2-7023-4d77-ba3d-e0d4194ec2b4"/>
<br />
<br />

<img src="https://github.com/user-attachments/assets/f13da5f2-7023-4d77-ba3d-e0d4194ec2b4"/>
<br />
<br />

<img src="https://github.com/user-attachments/assets/f13da5f2-7023-4d77-ba3d-e0d4194ec2b4"/>
<br />
<br />

<img src="https://github.com/user-attachments/assets/f13da5f2-7023-4d77-ba3d-e0d4194ec2b4"/>
<br />
<br />






![Screenshot (142)](https://github.com/user-attachments/assets/c14fa0af-0567-4b68-96d8-8bf26b8dd69f)
![Screenshot (141)](https://github.com/user-attachments/assets/408e62be-2826-4a22-b6fd-5cb660e607e8)
![Screenshot (140)](https://github.com/user-attachments/assets/5860dd2e-d4be-4a57-8a03-bacecf40021c)
![Screenshot (139)](https://github.com/user-attachments/assets/03194ed2-358f-4129-aa72-de0296d74a26)
![Screenshot (138)](https://github.com/user-attachments/assets/7b7459ef-c8a2-43db-9398-b5a862be8354)
![Screenshot (137)](https://github.com/user-attachments/assets/18fc6fa4-7df4-48a2-867d-bd9b0d385358)
![Screenshot (136)](https://github.com/user-attachments/assets/24b28c35-7ef2-482e-9950-4422d4fa3164)
![Screenshot (135)](https://github.com/user-attachments/assets/7e69586a-57d4-4f88-a99a-8185ba25648d)

![Screenshot (153)](https://github.com/user-attachments/assets/bfb4a6b6-9af0-438c-a87d-596a60d93000)
![Screenshot (152)](https://github.com/user-attachments/assets/da9b148c-ebae-460a-b07a-618b21f71abb)
![Screenshot (151)](https://github.com/user-attachments/assets/d112b3ed-f327-4206-b298-f019577d3655)
![Screenshot (150)](https://github.com/user-attachments/assets/871ea620-af35-4582-84fa-1d48d63a1c6d)
![Screenshot (149)](https://github.com/user-attachments/assets/d6e4b5c9-3d06-4d02-95eb-83740da1ffc8)
![Screenshot (148)](https://github.com/user-attachments/assets/f9595892-6ff0-4e96-8468-a62ba7ec76c7)
![Screenshot (147)](https://github.com/user-attachments/assets/463b7d9a-7425-4c1a-a7c7-f7103cbd1a6a)
![Screenshot (146)](https://github.com/user-attachments/assets/4698a30f-8b22-49a4-a223-6cfd18d95b43)


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
