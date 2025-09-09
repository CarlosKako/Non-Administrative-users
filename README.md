<p align="center">
<img width="700" height="379" alt="image" src="https://github.com/user-attachments/assets/b74fa3a6-2cd8-4cd3-90ac-79796ceb8e87" />

</p>
<h1>Non-Administrative-users</h1>
In this tutorial, we will learn how to set up Remote Desktop access for non-administrative users on Client-1, and then create multiple domain user accounts in Active Directory using a PowerShell script. By the end of the lab, we’ll be able to log into Client-1 with one of these newly created normal user accounts and test Remote Desktop connectivity.

<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Windows Server 2022

<h2>🔑 Prerequisites</h2>

You already have a working domain (mydomain.com).

You are logged into Client-1 with the account mydomain.com\jane_admin.

Active Directory is installed and running on DC-1.

</p>
<br />

<p>
<img width="1201" height="934" alt="image" src="https://github.com/user-attachments/assets/1a7af00d-4eef-4bd5-816f-122984f9ea7e" />


</p>
<p>
Enable Remote Desktop for Non-Administrative Users Log into Client-1 as mydomain.com\jane_admin. Press Windows + R, type sysdm.cpl, and hit Enter to open System Properties.

Go to the Remote tab.

Under Remote Desktop, select Allow remote connections to this computer.

Click on Select Users → Add.

Type Domain Users → click Check Names → then OK.

This gives all normal users in the domain permission to use RDP.

Apply and close the settings.

✅ Now, any non-administrative user in the domain can log into Client-1 via Remote Desktop.

</p>
<br />

<p>
<img width="1715" height="907" alt="image" src="https://github.com/user-attachments/assets/dd274482-7269-4cc5-8a63-4baee2f75cf9" />

</p>
<p>
  
Bulk Create Domain Users with PowerShell

Log into DC-1 as mydomain.com\jane_admin.

Open PowerShell ISE as Administrator.

Create a new script file and paste in the provided script (this script creates multiple new users in the _EMPLOYEES OU).

Save and run the script.

Observe the creation process in the PowerShell output.

Open Active Directory Users and Computers (ADUC).

Navigate to the _EMPLOYEES OU.

You should see all the newly created accounts listed.


</p>
<br />

<p>
<img width="974" height="533" alt="image" src="https://github.com/user-attachments/assets/7d4b2085-73dd-4ea4-bd0a-fa1c2b46ba9d" />


</p>
<p>
Test Remote Desktop with a Normal User

On Client-1, sign out of jane_admin.

Attempt to log into Client-1 using one of the new accounts created by the script.

Use the password defined in the script.

Confirm that the login is successful.
