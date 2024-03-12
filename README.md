<h1>Network File Shares and Permissions</h1>
In this tutorial, we will be working with network file shares and permissions. <br />

<h2>Environments and Technologies Used</h2>

- Microsoft Azure (Virtual Machines/Compute)
- Remote Desktop
- Various Command-Line Tools


<h2>Operating Systems Used </h2>

- Windows 10 (21H2)
- Windows Server

<h2>Actions and Observations</h2>

<p>
1.  Create some sample file shares with various permissions.  Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin).  Connect/log into Client-1 as a normal user (mydomain\<someuser>).  On DC-1, on the C:\ drive, create 4 folders: “read-access”, “write-access”, “no-access”, “accounting”.  

</p>
<p>
<img width="1512" alt="Screenshot 2024-03-11 at 7 41 50 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/d80fdc4f-7803-458e-a3ca-e73af4ed6fdb">


 </p>
<br />

<p>
1A.  Set the following permissions (share the folder) for the “Domain Users” group: Folder: “read-access”, Group: “Domain Users”, Permission: “Read” Folder: “write-access”,  Group: “Domain Users”, Permissions: “Read/Write” Folder: “no-access”, Group: “Domain Admins”, “Permissions: “Read/Write”.  (Skip accounting for now)  
</p>
<p>
<img width="1512" alt="Screenshot 2024-03-11 at 7 48 39 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/b990b3fa-4589-4d11-8e7f-5530fd88e61f">
<img width="1512" alt="Screenshot 2024-03-11 at 7 44 21 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/68d5b6fe-7f45-4eac-afb7-483bf7876bda">
<img width="1512" alt="Screenshot 2024-03-11 at 7 45 32 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/393f10a1-7fbd-4dfa-b303-522c5412924c">

 </p>
<br />

<p>
2.  Attempt to access file shares as a normal user.  On Client-1, navigate to the shared folder (start, run, \\dc-1).  Try to access the folders you just created. Which folders can you access? 
 Which folders can you create stuff in? Does it make sense?
  
</p>
<p>
 <img width="1512" alt="Screenshot 2024-03-11 at 7 54 23 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/1c417bbd-c697-420b-9cd9-ddd6c9f2db11">
<img width="1512" alt="Screenshot 2024-03-11 at 7 54 52 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/e0f4a124-b923-4eca-a6da-af6a69e3991a">
<img width="1512" alt="Screenshot 2024-03-11 at 7 55 26 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/7e757c3b-0450-4eb6-93a4-e987c38a4508">

 </p>
<br />

<p>
3.  Create an “ACCOUNTANTS” Security Group, assign permissions, and test access.  To do this go back to DC-1, in Active Directory, create a security group called “ACCOUNTANTS”.  
 
</p>
<p>
<img width="1512" alt="Screenshot 2024-03-11 at 8 04 30 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/a7c33dbe-4250-41a9-972e-d49ef464e3cd">

 </p>
<br />

<p>
3A.  On the “accounting” folder you created earlier, set the following permissions:  Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”.  

</p>
<p>
<img width="1512" alt="Screenshot 2024-03-11 at 8 05 53 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/1656663b-2135-4245-8b00-dd9d476bf04a">

 </p>
<br />

<p>
3B.  On Client-1, as  <someuser>, try to access the accountants folder. It should fail.  Log out of Client-1 as  <someuser>.  On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group.  Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?

</p>
<p>
<img width="1512" alt="Screenshot 2024-03-11 at 8 05 53 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/1656663b-2135-4245-8b00-dd9d476bf04a">

 </p>
<br />

<p>
3A.  On the “accounting” folder you created earlier, set the following permissions:  Folder: “accounting”, Group: “ACCOUNTANTS”, Permissions: “Read/Write”.  On Client-1, as  <someuser>, try to access the accountants folder. It should fail.  Log out of Client-1 as  <someuser>.  On DC-1, make <someuser> a member of the “ACCOUNTANTS”  Security Group.  Sign back into Client-1 as <someuser> and try to access the “accounting” share in \\DC-1\ - Does it work now?

</p>
<p>
<img width="1512" alt="Screenshot 2024-03-11 at 8 05 53 PM" src="https://github.com/richardwines32/Network_File_Shares_and_Permissions/assets/162821778/1656663b-2135-4245-8b00-dd9d476bf04a">

 </p>
<br />

