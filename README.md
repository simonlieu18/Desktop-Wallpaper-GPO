<p align="center">
<img src="https://i.imgur.com/G0Ls18P.png"/>
</p>

<h1>Group Policy Management</h1>
In this tutorial, we implement a new account lockout policy in Active Directory using Group Policy Management.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Group Policy Management Console
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022

<h2>High-Level Steps</h2>

- Add Group Policy Objects
- Configure Desktop Wallpaper policy
- Verify Policy with different departments

<h2>Configuration Steps</h2>

![image](https://github.com/user-attachments/assets/8e4a1a44-e0cf-42d5-a36f-b40b9a729893)

<p>
On the domain controller virtual machine created previously, in the Group Policy Management application locate "Group Policy Objects" and add a new policy called "Account Lockout Policy" or if there already is a policy linked to the domain then just skip this step.
</p>
<br />

![image](https://github.com/user-attachments/assets/388eb47f-8c69-41ab-92ff-ef8432f11254)

<p>
Edit the policy, navigate to "Account Lockout Policy" and configure the policy as needed.
</p>
<br />

![image](https://github.com/user-attachments/assets/ca55fe10-a157-4ac9-8da1-f049da1ee459)

<p>
Link the organizational unit/domain to the new policy that was created unless the policy was already connected.
</p>
<br />

![image](https://github.com/user-attachments/assets/3de7d8e1-79e0-44fc-85df-a723ee64e170)

<p>
Now on the client virtual machine, manually update the Group Policy by opening Powershell and inputting the command "gpudate /force". Then run the command "rsop.msc" to verify that the policy has been applied.
</p>
