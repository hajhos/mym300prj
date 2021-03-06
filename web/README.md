 ## Webserver

```
*--------------------------------------*
| Apache2                              |
| Virtualbox-6.1.2                     |
| Schulnetz 10.x.x.x (DHCP)            |
| Privates Netz 192.168.55.x (DHCP)    |           
| forwarded_port, guest:80, host:59465 |
| memory: 1024                         |
*--------------------------------------*
```
- Der Webserver-Vagranfile lokal speichern.
- Der Code nach eigene Anforderungen anpassen. 
```
*------------------------------------------------------------------------------*
| config.vm.network "forwarded_port", guest:80, host:59465, auto_correct: true |
| memory: 1024                                                                 |
*------------------------------------------------------------------------------*
````
- Vagrant starten.
``` 
cd c:/Users/hajar/mym300prj/web 
vagrant up 
```
- Die Dateien werden lokal auf dem Verzeichnis gespeichert.
- Webserver lauft auf dem Virtualbox.
- Die Weboberfläche ist unter der URL:**http://localhost:59465** erreichbar.
![](defaultpage.JPG)
- **Vagrantfile**, **Readme.md**, **Foto** und **.gitignore** auf dem Github-Repository pushen.

`Test`
- [x] Beim Aufruf der URL wird der Apache-Defaultseite angezeigt.
- [x] **Vagrantfile**, **Readme.md**, **Foto** und **.gitignore** sind erfolgreich auf dem Github-Repository gepusht.


##### Zurück zur LB2Dokumentation: https://github.com/hajhos/mym300prj/blob/master/LB2Dokumentation.md
