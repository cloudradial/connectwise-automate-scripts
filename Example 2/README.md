# CloudRadial Agent Scripts - iTernal Networks
**Contents** 

1. <u>Create CloudRadial Shortcut on Desktop.xml</u> – Script – This adds a shortcut to the portal on their desktop for ease of use for them (this script is also referenced in the agent installer script). 
2. <u>CloudRadial Agent installer.xml</u> – Script – This downloads a custom agent for the client and installs it on their Windows computers. It also runs the script above to create the shortcut. 
3. <u>Uninstall CloudRadial Agent.xml</u>  – Script – This is for offboarding if needed. 
4. <u>CloudRadial Installer.sql</u> – This adds the necessary additional fields to the client info section of Automate that provides information that the script needs. 
5. <u>CloudRadial Install Group.xml</u> – Group – This is a group that contains computers that are supposed to have CloudRadial, but don’t yet. This group has the script auto run to install the agent when the computer is online. 
6. <u>CloudRadial Agent Group.xml</u> – Group – This is a group that contains computers that already have the agent installed and monitors to make sure that the agent is running. 
7. <u>CloudRadial Installed Search.xml</u> – Search – This is the search that the CloudRadial Agent Group uses to add computers to the group. 
8. <u>CloudRadial not installed search.xml</u> – Search – This is the search that the CloudRadial Install Group uses to add computers to the group
9. <u>CloudRadial Agent Monitor.sql</u> – This monitors to make sure that the agent service is running. 



**Usage**

There are a few other things that need to be done in order for the scripts to work correctly. These should be done after importing each of the items mentioned above. 

1. We need to create the installation files for each client and save them to the following location on the LabTech/Automate server. L:\Transfer\Software\CloudRadial\

2. 1. In this folder we need to save the installer for each client from the CloudRadial portal. After       downloading each one, we need to zip each installer into it’s own zip file. Each file should look something like this ClientName-DataAgent-numbers.zip. 
   2. In this folder we also need to save a zip file that contains the ico and url shortcut files that       you want to copy to each desktop. You’ll need to create the URL file and the ico file first. The zip file needs to be named CloudRadial.zip for the script to grab it and install it. 

3. Each client that you want to install CloudRadial to will need the following things done in Automate. 

4. 1. Open the Client (double click on the client name)

   2. Click on the Info Tab

   3. Click on the CloudRadial tab (if this doesn’t exist then you need to run the CloudRadial Installer.sql file mentioned above. 

   4. Check the box for CloudRadial Enable

   5. Paste the name of the zip file for the client installer. This needs to match exactly the name of the zip file in step 1a above. It does not need the .zip in the file name. 

   6. Then click “Save Additional Information”

      ![Automate](https://itmedia.azureedge.net/media/content-000006.png)

Once you click save it will flag the client as being a client that should have CloudRadial installed on all of their computers/servers. Over time, the scripts will automatically run and start installing the agents to each system. 



**Special Thanks**

iTernal Networks - Michael Kanet & Darrell Null