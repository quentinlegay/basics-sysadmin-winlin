# Basics cheat-sheet sysadmin Windows & Linux
## Tester si un port est ouvert

### 🐧 Linux
```
telnet 192.168.1.10 3389
```
### 🪟 Windows (Powershell)
``` powershell
Test-NetConnection -ComputerName <IP> -Port <PORT>
```
``` powershell
tnc -cn <IP> -p <PORT>
```

## Emplacement du fichier host

### 🐧 Linux
```
/etc/hosts
```
### 🪟 Windows
```
C:\Windows\System32\drivers\etc\hosts
```

## Emplacement du fichier known_hosts

### 🐧 Linux
```
~/.ssh/known_hosts
```
### 🪟 Windows
```
C:\Users\%USERNAME%\.ssh\known_hosts
```

## Vérifier le hash d’un fichier

### 🐧 Linux
```
md5sum MonFichier.exe
sha1sum MonFichier.exe
sha256sum MonFichier.exe
```
### 🪟 Windows (Powershell)
``` powershell
Get-FileHash -Path "C:\Users\MonFichier.exe" -Algorithm SHA256
```

## Suivi en temps réel

### 🐧 Linux
```
tail -f /var/log/syslog
```
### 🪟 Windows (Powershell)
``` powershell
Get-Content -Path "C:\path\to\file.log" -Wait
```

## Historique des commandes

### 🐧 Linux
```
history
```
### 🪟 Windows (Powershell)

#### Session active
``` powershell
Get-History
```
#### Toutes les commandes tapées en powershell sur votre machine
``` powershell
cat -Path "$env:USERPROFILE\AppData\Roaming\Microsoft\Windows\PowerShell\PSReadLine\ConsoleHost_history.txt"
```

## Trouver une chaine de caractere dans des fichiers

### 🐧 Linux
```
grep -ir "error" /var/log/*
```
### 🪟 Windows
```
findstr /S /I "error" *
```

## Connexion réseau

### 🐧 Linux
```
netstat -laputen
```
### 🪟 Windows
```
netstat -an
```

### 🪟 Windows (Powershell)
```
Get-NetTCPConnection
```

## Log système

### 🐧 Linux
```
journalctl
```
### 🪟 Windows
```
eventvwr.msc
```

## Voir les utilisateurs connectés

### 🐧 Linux
```
who
```
### 🪟 Windows
```
query user
```

## Voir les taches planifiées

### 🐧 Linux
```
crontab -l
```
### 🪟 Windows
```
schtasks /query
```

## Connaître son IP publique

### 🐧 Linux
```
wget -qO- https://api.ipify.org
```
### 🪟 Windows (Powershell)
```
(Invoke-WebRequest -Uri "https://api.ipify.org").Content
```

## Afficher la table de routage

### 🐧 Linux
```
ip route
```
```
netstat -rn
```
### 🪟 Windows
```
route print
```

### 🪟 Windows (Powershell)
```
Get-NetRoute
```

## Afficher le débit temps réel d'une carte réseau

### 🪟 Windows
```
wmic nic where "NetEnabled=true" get Name, Speed
```

### 🪟 Windows (Powershell)
```
Get-NetAdapter
```