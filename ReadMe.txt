This repository is created to save the content created by user "C Sharp Conner" on the Microsoft Technet Gallery uploaded on the 26th of August 2016.
As the Technet Gallery has been closed (https://docs.microsoft.com/en-us/teamblog/technet-gallery-retirement) all code needed can now only be found on the WayBack machine (http://web.archive.org/web/20200318042633/https://gallery.technet.microsoft.com/SCSM-Last-Modified-Date-15425cdc#content) so this repository has been created to maintain this code going forward.
All rights to this code are not held by me.

This code is used to restore the Last Modified Dates of IR and SR work items within Microsoft System Center Service Manger (SCSM) after the installation of the Cireson Advanced Request Offering app.
The Advanced Request Offering app extends the IR and SR work item classes to add an additional property used by the Advanced Request Offering (ARO). As this changes the data on the work item by adding a new field and a value within that property, the Entity Change Log (ECL) records a change has been made and therefore overwrites the Last Modified date.
This can affect reporting on work items that use the lst modified date as a criteria. Running this code will set the Last modified date back to the date value available before the ARO app was installed.

Remember to always make backups as there is no undo button here. I have provided source code in case anyone is curious as to how this program works. I recommend using 7-Zip to unzip this file. As always, use at your own risk, I am not responsible for your actions, etc.