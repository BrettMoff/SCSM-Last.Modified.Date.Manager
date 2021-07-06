This repository is created to save the content created by user "C Sharp Conner" on the Microsoft Technet Gallery uploaded on the 26th of August 2016.
As the Technet Gallery has been closed (https://docs.microsoft.com/en-us/teamblog/technet-gallery-retirement) all code needed can now only be found on the WayBack machine (http://web.archive.org/web/20200318042633/https://gallery.technet.microsoft.com/SCSM-Last-Modified-Date-15425cdc#content) so this repository has been created to maintain this code going forward.
All rights to this code are not held by me.

This code is used to restore the Last Modified Dates of IR and SR work items within Microsoft System Center Service Manger (SCSM) after the installation of the Cireson Advanced Request Offering app.
The Advanced Request Offering app extends the IR and SR work item classes to add an additional property used by the Advanced Request Offering (ARO). As this changes the data on the work item by adding a new field and a value within that property, the Entity Change Log (ECL) records a change has been made and therefore overwrites the Last Modified date.
This can affect reporting on work items that use the lst modified date as a criteria. Running this code will set the Last modified date back to the date value available before the ARO app was installed.

============================= INSTRUCTIONS ============================= 
Welcome one and all, you may be wondering what this program is for.  Cireson has released Version 5 of their Portal.  After reading the fine print it turns out that after installing the Portal there's a management pack called "Cireson.AdvanceRequestOffering.mpb" which can be imported into SCSM to enhance functionality.  The downside is there's a price, all those Last Modified Dates for IR and SR Tickets that are in the Live SCSM Database will be changed to the date that this MPB gets imported.

Everyone must use downtime procedures, meaning no one is doing things in SCSM except you.
Now you use this program, enter the correct SCSM SQL Server and Database Name, then click the button "Load DataTable from SCSM SQL Database"
Depending on how many IRs and SRs are present, this can take a few seconds, be patient and wait for the DataTable list to appear
Congrats, you're now ready to click "Export DataTable to Save File" ... you'll notice it will save to the path where you will later load the save file.
Feel free to find and backup this save file if you're smart/nervous (cause you're smart).
Close the SCSM Last Modified Dates Manager Program for now..... open the SCSM Console
Now import the Cireson MPB called "Cireson.AdvanceRequestOffering" and watch as all your Last Modified Dates are assimilated
But you have a plan, and a save file, cause you've been following these steps in order proving you're smart... Close the SCSM Console
So after waiting a bit until SCSM settles down, open up the SCSM Last Modified Dates Manager Program again
Enter the correct SCSM SQL Server and Database Name, then click the button "Load Saved File" ...
You'll see it's loaded all of your correct last modified dates, fantastic, now click "Overrwrite SCSM SQL Database From Loaded DataTable"
Give it some time, there's quite a few entries to update, eventually a message box will pop-up
You've done it, you've proven your worth, a winner is you!
 

Note:  If you have already applied the Cireson MPB, you could be smart and just use an earlier backup of the database and restore it elsewhere, then grab the correct last modified dates and save them to the save file, then connect to the current Live SCSM Database and Overwrite the Last Modified Dates from there if your DW hasn't already synced.


Remember to always make backups as there is no undo button here. I have provided source code in case anyone is curious as to how this program works. I recommend using 7-Zip to unzip this file. As always, use at your own risk, I am not responsible for your actions, etc.