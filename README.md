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
<img width="1512" alt="Screenshot 2024-03-11 at 6 25 17 PM" src="https://github.com/richardwines32/DNS/assets/162821778/b9834df5-0199-44c9-899a-5d69ddbd6d27">
 </p>
<br />

<p>
1.  A-Record Exercise.  Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin).  Connect/log into Client-1 as an admin (mydomain\jane_admin).  From Client-1 try to ping “mainframe” notice that it fails.  
</p>
<p>
<img width="1512" alt="Screenshot 2024-03-11 at 6 25 17 PM" src="https://github.com/richardwines32/DNS/assets/162821778/b9834df5-0199-44c9-899a-5d69ddbd6d27">
 </p>
<br />

<p>
1.  A-Record Exercise.  Connect/log into DC-1 as your domain admin account (mydomain.com\jane_admin).  Connect/log into Client-1 as an admin (mydomain\jane_admin).  From Client-1 try to ping “mainframe” notice that it fails.  
</p>
<p>
<img width="1512" alt="Screenshot 2024-03-11 at 6 25 17 PM" src="https://github.com/richardwines32/DNS/assets/162821778/b9834df5-0199-44c9-899a-5d69ddbd6d27">
 </p>
<br />




