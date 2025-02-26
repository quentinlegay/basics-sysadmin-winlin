# Basics sysadmin Windows & Linux

- [Basics sysadmin Windows \& Linux](#basics-sysadmin-windows--linux)
  - [Tester si un port est ouvert](#tester-si-un-port-est-ouvert)
    - [🐧 Linux](#-linux)
    - [🪟 Windows](#-windows)
  - [Emplacement du fichier host](#emplacement-du-fichier-host)
    - [🐧 Linux](#-linux-1)
    - [🪟 Windows](#-windows-1)
  - [Emplacement du fichier known\_hosts](#emplacement-du-fichier-known_hosts)
    - [🐧 Linux](#-linux-2)
    - [🪟 Windows](#-windows-2)
  - [Vérifier le hash d’un fichier](#vérifier-le-hash-dun-fichier)
    - [🐧 Linux](#-linux-3)
    - [🪟 Windows](#-windows-3)
  - [Suivi en temps réel](#suivi-en-temps-réel)
    - [🐧 Linux](#-linux-4)
    - [🪟 Windows](#-windows-4)
  - [Historique des commandes](#historique-des-commandes)
    - [🐧 Linux](#-linux-5)
    - [🪟 Windows](#-windows-5)
  - [Trouver une chaine de caractere dans des fichiers](#trouver-une-chaine-de-caractere-dans-des-fichiers)
    - [🐧 Linux](#-linux-6)
    - [🪟 Windows](#-windows-6)

## Tester si un port est ouvert

### 🐧 Linux
```
telnet 192.168.1.10 3389
```
### 🪟 Windows
```
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
### 🪟 Windows
```
Get-FileHash -Path "C:\Users\MonFichier.exe" -Algorithm SHA256
```

## Suivi en temps réel

### 🐧 Linux
```
tail -f /var/log/syslog
```
### 🪟 Windows
```
Get-Content -Path "C:\path\to\file.log" -Wait
```

## Historique des commandes

### 🐧 Linux
```
history
```
### 🪟 Windows
```
Get-History
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
