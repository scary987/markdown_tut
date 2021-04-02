# Git und \("richtig"\) GitLab benutzen

## Projekt erstellen.

Loggt euch im (Git)[https://git.informatik.uni-rostock.de/users/sign_in] der Informatik an.
Erstellt ein Projekt.

Klont das Projekt iwo auf euer Festplatte mithilfe 
```sh
git clone <Link der zu dem Projekt fuehrt.>
```

## Bearbeiten

Einfach mithilfe des folgendes Befehls Aenderungen zum Commit hinzufügen.
```sh
git commit [Dateinamen]
```

## Hochladen
Normalerweise einfach
```sh
git push [-u Remoteprojekt] [Zweig]
```
hochladen. Da muesst staendig euer Password angeben und ich 
denke es ist auch nicht so sicher wie mit einem ssh-Schluessel.

Daher waere es ganz gut einfach einen Schluessel zu erstellen und diesen zu speichern.

### Linux

Unter Linux ist es am einfachsten und hier existieren auch mehrere Moeglichkeiten dafuer.
1. Evaluieren dieses Kommandos.
```bash
eval $\(ssh-agent\)
```
Danach muesste man mit ssh-add den dazugehoerigen private-Key hinzufuegen.
Das gilt aber nur fuer einen Shellinstanz und deswegen verweise ich nun auf 
das (Archlinuxwiki)[https://wiki.archlinux.org/index.php/SSH_keys#ssh-agent].
Besonders gut finde ich die Loesung mit systemd service.
Alternativ muesste man sich so ein initscript schreiben, was aber Aehnlichkeiten
zu dem anderen systemd service ausweisst.

### Windows 

Bei Windows einmal die Shell mit Administatorenrechten oeffnen.
Das braucht man fuer folgenden Befehl. Das aktiviert den openssh client, welcher normalerweise schon installiert ist.
```powershell
$OpenSSHClient = Get-WindowsCapability -Online | ? Name -like ‘OpenSSH.Client*’
Add-WindowsCapability -Online -Name $OpenSSHClient.Name
```
Dann muesst ihr mit derselben shell einmal einen ssh-agent service starten.
```powershell
$SSHAgentSvc = Get-Service -Name ‘ssh-agent’
Set-Service -Name $SSHAgentSvc.Name -StartupType Automatic
Start-Service -Name $SSHAgentSvc.Name
```
Und git sollte man manuell installieren unter diesem (Link)[https://git-scm.com/download/win].
Und dann mit ssh-add den Private Key hinzufuegen.

### MacOS
k.p :/
Ich habe keinen ueberteuerten Rechner.

### Ssh key generieren und in github hinzufuegen.

#### Windows und Linux

* mit RSA 
```sh
ssh-keygen -c [-P <Passwort>] -t rsa -b 4096
```
* mit Ed25519
```sh
 ssh-keygen -c [-P <Passwort>] -t ed25519 
```
Dann ist die Datei mit .pub der *Public* Key und der andere ist der *Private* Key.
Den *Public* Key muss man in den Einstellungen und `SSH Keys` hinzufuegen.
