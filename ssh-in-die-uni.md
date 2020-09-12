# SSH/SFTP in die UNI

## Warum SSH in die UNI? 

Vielleicht hast du mal im Linuxpool in der Uni gesessen, und Hausaufgaben gemacht, ein Gitrepo commited aber nicht gepusht, und jetzt kommst du an deine fertigen Dateien nicht mehr ran? :\(  
Vielleicht benutzt du selbst kein Linux, aber musst für Verteilte Systeme irgendwelche Middleware installieren?    
Kein Bock Python und Java aufm Heimrechner zu installieren ?   
  
So sorge nicht. Das alles kann man ja per SSH im Informatiknetz machen. Geht auch relativ fix.   
Man brauch aber einen zusätzlichen _**Informatikaccount**_. \([https://www.informatik.uni-rostock.de/it-service/informationen/nutzeraccount/](https://www.informatik.uni-rostock.de/it-service/informationen/nutzeraccount/)\)  
\(Ich frag mich immernoch, warum man das Remote-Desktop-Protokoll nicht im Linuxpool installiert hat.\)

### SSH installieren. 

Für folgende Betriebssysteme: 

* Windows
* Linux \(Arch, Debian\)
* MacOS

#### Windows

Für Windows 10+ könnt ihr SSH mit PowerShell benutzen. Einfach das benutzen.  
Ich glaube das gilt auch für neue Versionen von Windows 7 mit geupdateter PowerShell, bin mit aber nicht sicher.  
Ansonsten muss man Putty verwenden und installieren. \([https://www.putty.org/](https://www.putty.org/)\)

#### Linux \(Arch, Debian\)

Für beide Distributionen sollte SSH schon vorinstalliert sein. Falls doch nicht:

```text
#Arch, Manjaro etc.
    sudo pacman -Sy openssh
#Debian, Ubuntu, Mint etc.
    sudo apt update && sudo apt install openssh-client 
```

#### MacOS

Hier sollte SSH schon vorinstalliert sein. Ansonsten im Terminal:

```text
#brew muss installiert sein: https://brew.sh/index_de
    brew install openssh
```

### SSH

Wie der Name sagt, wird ein gesicherter Shellzugriff geöffnet. Falls du nicht weißt, wie man den bedient, Tutorials und Cheatsheets gibt es wie Sand am Meer. Hier ein gutes:  
[https://www2.icp.uni-stuttgart.de/~icp/mediawiki/images/b/bd/Sim\_Meth\_I\_T0\_cheat\_sheet\_10\_11.pdf](https://www2.icp.uni-stuttgart.de/~icp/mediawiki/images/b/bd/Sim_Meth_I_T0_cheat_sheet_10_11.pdf)

```text
ssh <KÜRZEL>@honshu.informatik.uni-rostock.de

#Do Something

exit #SSH beenden
```

### SFTP

Das wird tatsächlich benötigt um Dateien vom eigenem Rechner und dem Uniserver hin- und herzuschieben. Ähnlich wie SSH, aber man kann nur Dateien verschieben, hoch- \(put\) und runterladen. \(get\)   
Ansonsten einfach mal ins Manual gucken: [https://linux.die.net/man/1/sftp](https://linux.die.net/man/1/sftp)

```text
sftp <KÜRZEL>@honshu.informatik.uni-rostock.de
cd SOMEWHERE 
put Meins Server
get Meins HeimPC
exit #SFTP beenden
```

