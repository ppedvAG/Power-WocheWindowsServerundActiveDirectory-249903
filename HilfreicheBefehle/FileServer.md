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

## Storage Replica

```powershell
Test-SRTopology -SourceComputerName Server2 -SourceVolumeName F: -SourceLogVolumeName G: -DestinationComputerName Server3 -DestinationVolumeName F: -DestinationLogVolumeName G: -DurationInMinutes 1 -ResultPath E:\
```

```powershell
New-SRPartnership -SourceComputerName Server2 -SourceRGName rg02 -SourceVolumeName F: -SourceLogVolumeName G:  -DestinationComputerName Server3 -DestinationRGName rg03 -DestinationVolumeName F: -DestinationLogVolumeName G:
```

## Storage Spaces Direct

Zum erstellen des Storage Space Direct innerhalb des bestehenden Clusters.
```powershell
Enable-ClusterStorageSpacesdirect -cimSession s2dcluster
```
---
Zum erstellen eines Cluster Shared Volumes mit dem FileSystem ReFS in dem angelegten Storage Space Direct
```powershell
New-Volume -StoragePoolFriendlyName "S2d*" -FriendlyName s2dvol1 -Size 35GB -FileSystem CSVFS_ReFS
```