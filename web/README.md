 ## Webserver
```
*------------------------------------*
| Apache2                            |
| Virtualbox-6.1.2                   |
| Schulnetz 10.x.x.x (DHCP)          |
| Privates Netz 192.168.55.x (DHCP)  |           
*------------------------------------*
```
- Der Webserver-Vagranfile lokal speichern.
- Der Code nach eigene Anforderungen anpassen. 
- Vagrant up
``` 
cd c:/Users/hajar/mym300prj 
vagrant up 
```
- Die Dateien werden lokal auf dem Verzeichnis gespeichert.
- Die vagrantfile anpassen. (--> auf andere freie Port forwarden)
```
*------------------------------------------------------------------------------*
| config.vm.network "forwarded_port", guest:80, host:59465, auto_correct: true |
| memory: 1024                                                                 |
*------------------------------------------------------------------------------*
````
## Test
- [x] Beim Aufruf des URL wird der Apache-Defaultseite angezeigt.
- [x] vagrantfile ist erfolgreich gepusht.
