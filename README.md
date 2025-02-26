# Basics sysadmin Windows & Linux

Tester si un port est ouvert :

🐧 Linux :
```
telnet 192.168.1.10 3389
```
🪟 Windows : 
```
Test-NetConnection -ComputerName <IP> -Port <PORT>
```

Emplacement du fichier host :

🐧 Linux :
```
/etc/hosts
```
🪟 Windows :
```
C:\Windows\System32\drivers\etc\hosts
```

Emplacement du fichier known_hosts :

🐧 Linux :
```
~/.ssh/known_hosts
```
🪟 Windows :
```
C:\Users\%USERNAME%\.ssh\known_hosts
```

Vérifier le hash d’un fichier :

🐧 Linux :
```
md5sum MonFichier.exe
sha1sum MonFichier.exe
sha256sum MonFichier.exe
```
🪟 Windows :
```
Get-FileHash -Path "C:\Users\MonFichier.exe" -Algorithm SHA256
```

Suivi en temps réel :

🐧 Linux :
```
tail -f /var/log/syslog
```
🪟 Windows :
```
Get-Content -Path "C:\path\to\file.log" -Wait
```

Historique des commandes :

🐧 Linux :
```
history
```
🪟 Windows :
```
Get-History
```

Trouver une chaine de caractere dans des fichiers :

🐧 Linux :
```
grep -ir "error" /var/log/*
```
🪟 Windows :
```
findstr /S /I "error" *
```
