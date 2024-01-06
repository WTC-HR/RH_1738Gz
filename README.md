# RH_1738Gz
dont use the exe this a builded form the HR file 



## 🗑 Uninstaller (Removes the Scheduled Task, Script Folder and ExclusionPaths)
- Open a new Elevated Powershell Console and Paste the Contents below
```ps1
$ErrorActionPreference = "SilentlyContinue"
function Cleanup {
  Unregister-ScheduledTask -TaskName "HR" -Confirm:$False
  Remove-Item -Path "$env:appdata\HR" -force -recurse
  Remove-MpPreference -ExclusionPath "$env:APPDATA\HR"
  Remove-MpPreference -ExclusionPath "$env:LOCALAPPDATA\Temp"
  Write-Host "[~] Successfully Uninstalled !" -ForegroundColor Green
}
Cleanup
```
