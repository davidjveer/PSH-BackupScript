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

NOTE:  You may have to change the PowerShell ExecutionPolicy on your local system in order to run local scripts, see below:

```
PS C:\PSH-BackupScript> Get-ExecutionPolicy
Restricted
PS C:\PSH-BackupScript>
PS C:\PSH-BackupScript> Set-ExecutionPolicy -ExecutionPolicy RemoteSigned
```

If *RemoteSigned* doesn't work for your system you can `Get-Help Set-ExecutionPolicy` to find the correct policy for your use cases.
