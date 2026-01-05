<p align="center">
<img src="https://i.imgur.com/G0Ls18P.png"/>
</p>

<h1>Desktop Wallpaper GPO</h1>
In this tutorial, we implement a desktop wallpaper policy in Active Directory using Group Policy Management.<br />



<h2>Environments and Technologies Used</h2>

- Microsoft Azure/Hyper-V
- Remote Desktop
- Group Policy Management Console
- Active Directory Domain Services

<h2>Operating Systems Used </h2>

- Windows Server 2022
- Windows Server 2025

<h2>High-Level Steps</h2>

- Create Shareable Folder
- Configure Desktop Wallpaper policy
- Verify Policy with Different Departments

<h2>Configuration Steps</h2>

<img width="671" height="579" alt="Screenshot 2026-01-05 at 2 08 40 PM" src="https://github.com/user-attachments/assets/457fc520-9a6b-41a0-8f20-0be5ecdc6031" />

<p>
First, a sharable folder needs to be created so that different departments are able to access the correct image for their wallpaper. To do that, a new folder will need to be created in the "C:" drive of the domain controller VM. After that, the folder's properties will need to be adjusted so that it will be shareable. By going into properties, sharing tab, advanced sharing, and then having "Share this folder" checked.
</p>
<br />

<img width="1212" height="636" alt="Screenshot 2026-01-05 at 2 15 21 PM" src="https://github.com/user-attachments/assets/06266e8c-e5a1-43ac-b1cf-4f3ed7801a80" />

<p>
Now, on the client VM, sign in as a user to verify that the folder has been shared correctly. To view the folder, open the folder explorer application and input "\\HOSTNAME". In order to find hostname of your DC, open command line/powershell and type in hostname on your DC VM.
</p>
<br />

<img width="929" height="382" alt="Screenshot 2026-01-05 at 2 22 40 PM" src="https://github.com/user-attachments/assets/4e0622a3-76a5-470a-afbe-413004687bfa" />

<p>
Next, input the images into the shareable folder that will be used for the desktop wallpapers.
</p>
<br />

<img width="372" height="94" alt="Screenshot 2026-01-05 at 2 26 02 PM" src="https://github.com/user-attachments/assets/25a1bec7-59a1-4239-bfb3-c46eee130714" />

<p>
In the Group Policy Management application, locate "Group Policy Objects" and add a new policy called "Desktop Wallpaper Policy" along with the department name if needed.
</p>
<br />

![image](https://github.com/user-attachments/assets/3de7d8e1-79e0-44fc-85df-a723ee64e170)

<p>
Now on the client virtual machine, manually update the Group Policy by opening Powershell and inputting the command "gpudate /force". Then run the command "rsop.msc" to verify that the policy has been applied.
</p>
