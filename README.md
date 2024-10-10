<p align="center">
<img src="https://i.imgur.com/Clzj7Xs.png" alt="osTicket logo"/>
</p>


osTicket - Ticket Lifecycle

This tutorial outlines the lifecycle of a ticket in osTicket.

Environments and Technologies Used

	•	Microsoft Azure (Virtual Machines/Compute)
	•	Remote Desktop
	•	Internet Information Services (IIS)
	•	osTicket

Operating Systems Used

	•	Windows 10

Prerequisites --> <a href="https://github.com/simeonhawkins/ticket-lifecycle"> Post Install Configuration </a>

	
	•	Be connected to the Windows VM via RDP.
	•	Logged into osTicket.

Objectives

In the final part of the osTicket tutorial series, we will demonstrate the complete lifecycle of a ticket, from creation and triage to closure by both an agent and a user. Additionally, we will go over the steps to properly clean up resources in Azure after completing the tutorial.

Ticket Lifecycle

Step 1: Log in as Admin

The first step in the ticket lifecycle is to log in as the Admin in osTicket. We will use the Admin role to triage tickets for the employees and set SLAs based on ticket severity.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955063-07231646-344e-4564-bd1c-1a5f1eb83e1d.png" height="80%" width="80%" alt="Admin Login"/>
</p>


Step 2: Create a New Ticket as a User

	•	Open a new browser tab and go to http://localhost/osTicket/.
	•	Click Open a New Ticket. This simulates a user, either internal or external, creating a ticket for their issue.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955126-ecb4be01-0183-4d6d-b0d9-22fbf125fa76.png" height="80%" width="80%" alt="Create a New Ticket"/>
</p>


Step 3: Fill in the Ticket Details

	•	For Name and Email, enter details of one of the users created previously (e.g., GregD@osTicket.com).
	•	For Help Topic, select Severe Outage.
	•	For Issue Summary, enter a brief description such as “Server is unresponsive.”
	•	Click Create Ticket.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955137-fe571b38-a9c6-4bba-81e7-474830e3b4de.png" height="80%" width="80%" alt="Fill Ticket Details"/>
</p>


Step 4: Create Additional Tickets

	1.	Connection Issue:
	•	User: GregD@osTicket.com
	•	Issue Summary: “A website is taking a long time to load.”
	•	This will be a lower SLA since the issue is less severe.
	2.	Password Reset:
	•	User: PeleT@osTicket.com
	•	Issue Summary: “Password needs to be reset.”
	•	This is a common issue and will be handled by a Level 1 support team member.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955150-c3b608d9-5712-4892-8bc6-9340c28f1437.png" height="80%" width="80%" alt="Create Connection Issue Ticket"/>
<img src="https://user-images.githubusercontent.com/128980344/232955167-63c64534-1917-453d-bac6-d94e3bd4c763.png" height="80%" width="80%" alt="Create Password Reset Ticket"/>
</p>


Step 5: Triage Tickets as Admin

	•	Switch back to the Admin Panel and go to Tickets.
	•	You should see the three newly created tickets.

	1.	Server Down:
	•	Change Priority to High and SLA to Sev-A.
	•	Assign the Department to System Administrators.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955183-672ed803-4117-477f-bb26-e06154727bf9.png" height="80%" width="80%" alt="Triage Server Down Ticket"/>
</p>


	2.	Slow Website:
	•	Change Priority to High and SLA to Sev-B.
	•	Assign the Department to Network Department.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955217-c620c9dd-a4c6-480a-8146-8d91d15db421.png" height="80%" width="80%" alt="Triage Slow Website Ticket"/>
</p>


	3.	Password Reset:
	•	Change Priority to Low and SLA to Sev-C.
	•	Keep the Department unchanged.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955231-dceff127-eff8-4d84-a548-79891c3a8ffa.png" height="80%" width="80%" alt="Triage Password Reset Ticket"/>
</p>


Step 6: Close the Tickets

	1.	Password Reset:
	•	As the support agent, respond to the ticket stating that the password has been reset.
	•	Set the status to Closed and click Post Reply.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955334-36ca40c1-11cf-45b0-81fc-29e05cfa59b1.png" height="80%" width="80%" alt="Close Password Reset Ticket"/>
</p>


	2.	Server Down:
	•	Log in as Jessica (Jess_Vaner / Password12321).
	•	Respond to the ticket, set it to Resolved, and Post Reply.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955377-93b14440-200a-4d56-b4fb-ee1f576e9094.png" height="80%" width="80%" alt="Close Server Down Ticket"/>
</p>


	3.	Slow Website:
	•	Log in as David (David_Bale / Password12321).
	•	Respond to the ticket, set it to Resolved, and Post Reply.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955376-69f169ba-7198-4896-86ed-75adaa0cb8d4.png" height="80%" width="80%" alt="Close Slow Website Ticket"/>
</p>


Step 7: Check Ticket Status

	•	As a user, go to the Check Ticket Status page to view the resolved tickets.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955345-4dea89e8-3b6c-4e12-af56-991eef2ba9e3.png" height="80%" width="80%" alt="Check Ticket Status"/>
</p>


Resource Cleanup

Now that we are done with osTicket, we can clean up our resources in Azure:

	1.	Disconnect from the VM:
Right-click and close the RDP window.
	2.	Go to the Azure Portal and navigate to the Resource Group you created.
	3.	Click Delete Resource Group and confirm by typing the resource group name.

<p align="center">
<img src="https://user-images.githubusercontent.com/128980344/232955378-5dbb6e1f-d0e0-45fd-b056-485e334610e2.png" height="80%" width="80%" alt="Delete Resource Group"/>
</p>


This concludes the tutorial series. Thank you for following along! If you have any feedback or would like to connect, feel free to reach out on LinkedIn.
