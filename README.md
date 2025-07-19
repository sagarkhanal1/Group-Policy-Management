<h1>GPO Configuration Project</h1>

<h2>Description</h2>
<!-- Documenting the configuration of Group Policy Objects in a Windows Server environment -->
This project extends the SAGARDOMAIN setup by implementing Group Policy Objects (GPOs) to enforce password policies and desktop lockdown settings. It utilizes the existing Active Directory infrastructure to manage user and computer configurations, with detailed steps captured in screenshots.
<br />

<h2>Languages and Utilities Used</h2>
<!-- Listing the tools and utilities utilized in the project -->
<ul>
    <li><b>Group Policy Management Console (GPMC)</b></li>
    <li><b>Active Directory Users and Computers</b></li>
</ul>

<h2>Environments Used</h2>
<!-- Specifying the operating systems used in the project -->
<ul>
    <li><b>Windows Server 2022</b> (Domain Controller)</li>
    <li><b>Windows 10</b> (21H2) (Client)</li>
</ul>

<h2>Project Walk-through:</h2>
<p style="font-size: 20px;">
<b>
<!-- Accessing Group Policy Management Console -->
Accessing Group Policy Management Console: <br/><br />
<img src="https://i.imgur.com/joEY6jG.png" height="80%" width="80%" alt="GPMC Access"/>
<br />
<span style="font-size: 16px;">The Group Policy Management Console (GPMC) is opened on the Domain Controller to begin configuring GPOs for SAGARDOMAIN.</span>
<br />
<br />
<!-- Creating a New GPO for Password Policy -->
Creating a New GPO for Password Policy: <br/><br />
<img src="https://i.imgur.com/JTCa5sN.png" height="80%" width="80%" alt="New GPO Password"/>
<br />
<span style="font-size: 16px;">A new GPO named SAGARDOMAIN_PasswordPolicy is created and linked to the domain root to enforce password complexity and expiration settings.</span>
<br />
<br />
<!-- Configuring Password Policy Settings -->
Configuring Password Policy Settings: <br/><br />
<img src="https://i.imgur.com/l7V5nCE.png" height="80%" width="80%" alt="Password Settings"/>
<img src="https://i.imgur.com/IwGvUbH.png" height="80%" width="80%" alt="Password Settings"/>
<br />
<span style="font-size: 16px;">Password settings are configured, requiring a minimum length of 12 characters, complexity, and a 90-day expiration period.</span>
<br />
<br />
<!-- Creating a New GPO for Desktop Lockdown -->
Creating a New GPO for Desktop Lockdown: <br/><br />
<img src="https://i.imgur.com/0KARzyU.png" height="80%" width="80%" alt="New GPO Desktop"/>
<br />
<span style="font-size: 16px;">A new GPO named SAGARDOMAIN_DesktopLockdown is created and linked to the Users OU to restrict desktop access for standard users.</span>
<br />
<br />
<!-- Configuring Desktop Lockdown Settings -->
Configuring Desktop Lockdown Settings: <br/><br />
<img src="https://i.imgur.com/npvxY6D.png" height="80%" width="80%" alt="Desktop Lockdown"/>
<img src="https://i.imgur.com/qozHwAu.png" height="80%" width="80%" alt="Desktop Lockdown"/>
<img src="https://i.imgur.com/BZyu3Tp.png" height="80%" width="80%" alt="Desktop Lockdown"/>
<br />
<span style="font-size: 16px;">Settings are applied to disable USB ports, restrict Control Panel access, and prevent software installations on client machines.</span>
<br />
<br />
<!-- Linking GPOs to Organizational Unit -->
Linking GPOs to Organizational Unit: <br/><br />
<img src="https://i.imgur.com/n3j06Xb.png" height="80%" width="80%" alt="New GPO Desktop"/>
<br />
<span style="font-size: 16px;">The SAGARDOMAIN_PasswordPolicy GPO is linked to the domain, while SAGARDOMAIN_DesktopLockdown is linked to the Users OU for targeted application.</span>
<br />
<br />
<!-- Verifying GPO Application on Client -->
Verifying GPO Application on Client: <br/><br />
<img src="https://i.imgur.com/kl2avWo.png" height="80%" width="80%" alt="GPO Verification"/>
<br />
<span style="font-size: 16px;">The Windows 10 client (CLIENT1) is restarted, and gpupdate /force is run to apply the GPOs, with settings verified through local policy checks.</span>
<br />
<br />
<!-- Testing Password Policy Enforcement -->
Testing Password Policy Enforcement: <br/><br />
<img src="https://i.imgur.com/ftO6i0j.png" height="80%" width="80%" alt="Password Test"/>
<br />
<span style="font-size: 16px;">A user attempts to set a weak password, and the system enforces the 12-character complexity rule, confirming policy success.</span>
<br />
<br />
<!-- Testing Desktop Lockdown Enforcement -->
Testing Desktop Lockdown Enforcement: <br/><br />
<img src="https://i.imgur.com/RArv071.png" height="80%" width="80%" alt="Desktop Test"/>
<br />
<span style="font-size: 16px;">A standard user tries to access the Control Panel or install software on CLIENT1, and the restrictions are successfully enforced.</span>
<br />
<br />
</b>
</p>
