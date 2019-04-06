# PowerShell/BackupScript
Basic script for backing up Windows directories and files with PowerShell

**Scripts are provided with no warranty or guarantee, use at your own risk!**

The TOP of the script includes some varables to change in order to suit your needs.

It includes things like the location to copy the files to, how many backups you want to keep,
what directories to back up, any exclusions, etc.

Each variable has a brief comment after it to describe what it's used for.

NOTE:  Email report via SMTP is disabled by **$SendEmail** so you'll have to change
that to *$true* if you'd like to enable that functionality and also set the TO, FROM
and SMTP server settings.

_See the example below:_
#Variables, only Change here
$Destination="C:\Users\Donna" #Copy the Files to this Location
$TempDir="C:\TEMP"
$Versions="8" #How many of the last Backups you want to keep
$BackupDirs="C:\Users\Donna\", "C:\Program Files (x86)\OpenVPN" #What Folders you want to backup
$ExcludeDirs="C:\Users\Donna\OneDrive", "C:\Program Files (x86)\OpenVPN\config" #This list of Directories will not be copied
$LogName="Log.txt" #Log Name
$LoggingLevel="3" #LoggingLevel only for Output in Powershell Window, 1=smart, 3=Heavy
$Zip=$true #Zip the Backup Destination
$RemoveBackupDestination=$false #Remove copied files after Zip, only if $Zip is true


#Send Mail Settings
$SendEmail = $false                    # = $true if you want to enable send report to e-mail (SMTP send)
$EmailTo   = 'test@domain.com'              #user@domain.something (for multiple users use "User01 &lt;user01@example.com&gt;" ,"User02 &lt;user02@example.com&gt;" )
$EmailFrom = 'from@domain.com'   #matthew@domain 
$EmailSMTP = 'smtp.domain.com' #smtp server adress, DNS hostname.
