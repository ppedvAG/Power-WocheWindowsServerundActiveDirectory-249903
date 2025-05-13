# FileServer

## Nützliche PowerShell-Befehle für die Dateidienste

Zum Evaluieren ob sich die Datendeduplizierung lohnt.
```powershell
C:\Windows\System32\ddpeval.exe E:
```
---
Zum manuellen starten der Datendeduplizierung.
```powershell
Start-DedupJob -Volume E: -Type Optimization
```
---
Zum Abfragen ob aktuelle DedupJobs laufen.
```powershell
Get-DedupJob
```