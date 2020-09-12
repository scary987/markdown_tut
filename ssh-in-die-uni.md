# SSH in die UNI

## Warum SSH in die UNI? 

Vielleicht hast du mal im Linuxpool in der Uni gesessen, und Hausaufgaben gemacht, ein Gitrepo commited aber nicht gepusht, und jetzt kommst du an deine fertigen Dateien nicht mehr ran? :\(  
Vielleicht benutzt du selbst kein Linux, aber musst für Verteilte Systeme irgendwelche Middleware installieren?    
Kein Bock Python und Java aufm Heimrechner zu installieren ?   
  
So sorge nicht. Das alles kann man ja per SSH im Informatiknetz machen. Geht auch relativ fix.  
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


#### MacOS

Hier sollte SSH schon vorinstalliert sein. Ansonsten im Terminal:

```text
#brew muss installiert sein: https://brew.sh/index_de
    brew install openssh
```



