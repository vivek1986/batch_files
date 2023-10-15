# batch_files1

### Batch(BAT/CMD) code for lowering screen brightness:
```bat
Powershell "(Get-WmiObject -Namespace root/WMI -Class WmiMonitorBrightnessMethods).WmiSetBrightness(1, 8)"
```
```cmd
Powershell "(Get-WmiObject -Namespace root/WMI -Class WmiMonitorBrightnessMethods).WmiSetBrightness(1, 8)"
```

### PowerShell(PwSh) code for lowering screen brightness:
```ps1
(Get-WmiObject -Namespace root/WMI -Class WmiMonitorBrightnessMethods).WmiSetBrightness(1, 8)
```
```psm1
(Get-WmiObject -Namespace root/WMI -Class WmiMonitorBrightnessMethods).WmiSetBrightness(1, 8)
```
```psd1
(Get-WmiObject -Namespace root/WMI -Class WmiMonitorBrightnessMethods).WmiSetBrightness(1, 8)
```

### My PowerShell User Profile Script:
```ps1
### Profile Folder Path: "%USERPROFILE%\Documents\WindowsPowerShell"
### Profile Directory Path: "%USERPROFILE%\Documents\WindowsPowerShell"
### Profile File Path: "%USERPROFILE%\Documents\WindowsPowerShell\profile.ps1"
### This Script's Path: "%USERPROFILE%\Documents\WindowsPowerShell\profile.ps1"
### Profile Script Path: "%USERPROFILE%\Documents\WindowsPowerShell\profile.ps1"

function Create-User-Profile-Script {
    if (!(Test-Path -Path $PROFILE )) { New-Item -Type File -Path $PROFILE -Force }
    if (!(Test-Path -Path $PROFILE.AllUsersCurrentHost)) { New-Item -Type File -Path $PROFILE.AllUsersCurrentHost -Force }
    if (!(Test-Path -Path $PROFILE.CurrentUserAllHosts)) { New-Item -Type File -Path $PROFILE.CurrentUserAllHosts -Force }
    if (!(Test-Path -Path $PROFILE.AllUsersAllHosts)) { New-Item -Type File -Path $PROFILE.AllUsersAllHosts -Force }
}

function Remove-EmptyDirectories0 {
    param([string]$path)
    Get-ChildItem "$Path" -Recurse -Force -Directory | Sort-Object -Property FullName -Descending | Where-Object { $($_ | Get-ChildItem -Force | Select-Object -First 1).Count -eq 0 } | Remove-Item -Verbose
}
Remove-EmptyDirectories0 -path "$ENV:APPDATA"
Remove-EmptyDirectories0 -path "$ENV:LOCALAPPDATA"
Remove-EmptyDirectories0 -path "$env:UserProfile\Documents"

function Clear-History0 {
    Clear-History; Remove-Item -Force (Get-PSReadlineOption).HistorySavePath; Clear-History; CLS; Exit;
}
```
```psm1
### Profile Folder Path: "%USERPROFILE%\Documents\WindowsPowerShell"
### Profile Directory Path: "%USERPROFILE%\Documents\WindowsPowerShell"
### Profile File Path: "%USERPROFILE%\Documents\WindowsPowerShell\profile.ps1"
### This Script's Path: "%USERPROFILE%\Documents\WindowsPowerShell\profile.ps1"
### Profile Script Path: "%USERPROFILE%\Documents\WindowsPowerShell\profile.ps1"

function Create-User-Profile-Script {
    if (!(Test-Path -Path $PROFILE )) { New-Item -Type File -Path $PROFILE -Force }
    if (!(Test-Path -Path $PROFILE.AllUsersCurrentHost)) { New-Item -Type File -Path $PROFILE.AllUsersCurrentHost -Force }
    if (!(Test-Path -Path $PROFILE.CurrentUserAllHosts)) { New-Item -Type File -Path $PROFILE.CurrentUserAllHosts -Force }
    if (!(Test-Path -Path $PROFILE.AllUsersAllHosts)) { New-Item -Type File -Path $PROFILE.AllUsersAllHosts -Force }
}

function Remove-EmptyDirectories0 {
    param([string]$path)
    Get-ChildItem "$Path" -Recurse -Force -Directory | Sort-Object -Property FullName -Descending | Where-Object { $($_ | Get-ChildItem -Force | Select-Object -First 1).Count -eq 0 } | Remove-Item -Verbose
}
Remove-EmptyDirectories0 -path "$ENV:APPDATA"
Remove-EmptyDirectories0 -path "$ENV:LOCALAPPDATA"
Remove-EmptyDirectories0 -path "$env:UserProfile\Documents"

function Clear-History0 {
    Clear-History; Remove-Item -Force (Get-PSReadlineOption).HistorySavePath; Clear-History; CLS; Exit;
}
```
