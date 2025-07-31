# Basics sysadmin Windows & Linux

- [Basics sysadmin Windows \& Linux](#basics-sysadmin-windows--linux)
  - [Tester si un port est ouvert](#tester-si-un-port-est-ouvert)
    - [🐧 Linux](#-linux)
    - [🪟 Windows (Powershell)](#-windows-powershell)
  - [Emplacement du fichier host](#emplacement-du-fichier-host)
    - [🐧 Linux](#-linux-1)
    - [🪟 Windows](#-windows)
  - [Emplacement du fichier known\_hosts](#emplacement-du-fichier-known_hosts)
    - [🐧 Linux](#-linux-2)
    - [🪟 Windows](#-windows-1)
  - [Vérifier le hash d’un fichier](#vérifier-le-hash-dun-fichier)
    - [🐧 Linux](#-linux-3)
    - [🪟 Windows (Powershell)](#-windows-powershell-1)
  - [Suivi en temps réel](#suivi-en-temps-réel)
    - [🐧 Linux](#-linux-4)
    - [🪟 Windows (Powershell)](#-windows-powershell-2)
  - [Historique des commandes](#historique-des-commandes)
    - [🐧 Linux](#-linux-5)
    - [🪟 Windows (Powershell)](#-windows-powershell-3)
      - [Session active](#session-active)
      - [Toutes les commandes tapées en powershell sur votre machine](#toutes-les-commandes-tapées-en-powershell-sur-votre-machine)
  - [Trouver une chaine de caractere dans des fichiers](#trouver-une-chaine-de-caractere-dans-des-fichiers)
    - [🐧 Linux](#-linux-6)
    - [🪟 Windows](#-windows-2)
  - [Connexion réseau](#connexion-réseau)
    - [🐧 Linux](#-linux-7)
    - [🪟 Windows](#-windows-3)
    - [🪟 Windows Powershell](#-windows-powershell-4)
  - [Log système](#log-système)
    - [🐧 Linux](#-linux-8)
    - [🪟 Windows](#-windows-4)
  - [Voir les utilisateurs connectés](#voir-les-utilisateurs-connectés)
    - [🐧 Linux](#-linux-9)
    - [🪟 Windows](#-windows-5)
  - [Voir les taches planifiées](#voir-les-taches-planifiées)
    - [🐧 Linux](#-linux-10)
    - [🪟 Windows](#-windows-6)

## Tester si un port est ouvert

### 🐧 Linux
```
telnet 192.168.1.10 3389
```
### 🪟 Windows (Powershell)
``` powershell
Test-NetConnection -ComputerName <IP> -Port <PORT>
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

### 🪟 Windows Powershell
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