# Allgemeine  Befehle

Für die es sonst keinen Platz gibt
---

Zum umbennen von PCs
```powershell
Rename-Computer -NewName Server3
```

---
Zum hinzufügen eines PCs zur Domäne
```powershell
Add-Computer -Domainname ppedv.test
```

---
Zur Abfrage der Verteilung der FSMO Rollen
```powershell
netdom query fsmo
```

--- 
Zum Abfragen aller Features und deren Installationsstatus
```powershell
Get-WindowsFeature
```
Zum Installieren von zwei Features auf zwei Remote Server nacheinander mit automatischen Neustart und den dazugehörigen Verwaltungstools

```powershell
Invoke-Command -ComputerName Server2,Server3 -ScriptBlock {Install-WindowsFeature -Name FS-FileServer,Storage-Replica -IncludeManagementTools -Restart}
```