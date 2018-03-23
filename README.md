# Sharepoint backup database (.bak) and mount to another sites
Powershell backup database of sharepoint and update to another sites
use "sharepoint management shell" with administrator to do it.

<h1>Backup</h1>
<p>Backup-SPSite http://sitename -Path "Path file .bak in computer"</p>
<p>EX: Backup-SPSite http://test.com/sites/ServicePortal -Path C:\Users\Public\Documents\spintra-dev.bak</p>
ref: https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/backup-spsite?view=sharepoint-ps

<h1>Mount Database to another sites</h1>
<p>Mount-SPContentDatabase "MyDatabase" -DatabaseServer "MyServer" -WebApplication http://sitename</p>
<p>EX: Mount-SPContentDatabase WSS_Content_test -DatabaseServer THSP0001 -WebApplication https://tha-spintra.devtest.com</p>
//"MyDatabase" can see real name by right click your database and select properties, the database name will show in it.
//"MyServer" is hostname
ref: https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/mount-spcontentdatabase?view=sharepoint-ps

<h1>If database that backup is not work can backup again and get new .bak file to restore by</h1>
<p>EX: Restore-SPSite http://test.com/sites/ServicePortal -Path C:\Users\Public\Documents\spintra-dev.bak -Force</p>
ref: https://docs.microsoft.com/en-us/powershell/module/sharepoint-server/restore-spsite?view=sharepoint-ps
