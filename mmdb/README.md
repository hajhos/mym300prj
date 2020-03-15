 ## Multi Machine DB

```
*--------------------------------------------------------------*
| Notebook, Homenetz 192.168.1.0 und Privates Netz 192.168.2.0 |                 
| Port: 8080 (192.168.2.201:80)                                |
| Virtualbox-6.1.2                                             |
|	
	    -
     |   NET-ID: 192.168.2.0  |
     |------------|------------|------------|
     |  Server    |Web-Server: apache2 |DB-Sever: mysql |
     | Hostname   |lb2web              |lb2db           |
     
   
     
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
cd c:/Users/hajar/mym300prj 
vagrant up 
```
- Die Dateien werden lokal auf dem Verzeichnis gespeichert.
- Webserver lauft auf dem Virtualbox.
- Die Weboberfläche ist unter der URL:**http://localhost:59465** erreichbar.

`Test`
- [x] Beim Aufruf der URL wird der Apache-Defaultseite angezeigt.
- [x] Vagrantfile ist erfolgreich auf dem Github-Repository gepusht.





Multi Machine Beispiel


### Übersicht 

    +---------------------------------------------------------------+
    ! Notebook - Schulnetz 10.x.x.x und Privates Netz 192.168.55.1  !                 
    ! Port: 8080 (192.158.55.101:80)                                !	
    !                                                               !	
    !    +--------------------+          +---------------------+    !
    !    ! Web Server         !          ! Datenbank Server    !    !       
    !    ! Host: web01        !          ! Host: db01          !    !
    !    ! IP: 192.168.55.101 ! <------> ! IP: 192.168.55.100  !    !
    !    ! Port: 80           !          ! Port 3306           !    !
    !    ! Nat: 8080          !          ! Nat: -              !    !
    !    +--------------------+          +---------------------+    !
    !                                                               !	
    +---------------------------------------------------------------+
	
### Beschreibung

* Web Server mit Apache und MySQL UserInterface [Adminer](https://www.adminer.org/)
* Datenbank Server mit MySQL

* Die Verbindung Web - Datenbank erfolgt mittels Internen Netzwerk Adapter.
* Von Aussen ist nur der HTTP Port auf dem Web Server Erreichbar.

Um in die VM zu wechseln ist zusätzlich der in Vagrantfile definierte Name einzugeben.

	vagrant ssh database
	vagrant ssh web

Das MySQL User Interface ist via [http://localhost:8080/adminer.php](http://localhost:8080/adminer.php) mit User/Password: root/admin erreichbar.

### Tests

* keine

### Sicherheit

* Datenbank Server bzw. MySQL ist mit Password geschützt.
* Der Web Server ist offen und mittels ungeschütztem HTTP Protokoll erreichbar.
