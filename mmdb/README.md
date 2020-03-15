 ## Multi Machine DB

```
*--------------------------------------------------------------*
| Notebook                                                     |
| Homenetz: 192.168.1.0                                        |
| Privates Netz: 192.168.2.0                                   |                 
| Port: 8080 (192.168.2.201:80)                                |
| Virtualbox-6.1.2                                             |
*--------------------------------------------------------------*	
```
| Server              | Hostname            | IP-Adresse          | Netz                | Port                |
|:--------------------|:--------------------|:--------------------|:--------------------|:--------------------|
| Web-Server: apache2 | lb2web              | 192.168.2.201       | NAT: 80             | 8080                |
| DB-Server: mysql    | lb2db               | 192.168.2.200       | __                  | 3306                |

- Der mmdb-Vagranfile lokal speichern.
- Der Code nach eigene Anforderungen anpassen. 
- Beim IP-Anpassungen muss diese Änderung auf dem **db.sh** auch eingetragen werden.
- Die Server (mysql & apache2) sind im gleichen Netz. 
- Die Änderungen speichern. (auf vim -> :wq)
- Vagrant up
``` 
cd c:/Users/hajar/mym300prj/mmdb 
vagrant up 
```
- **Vagrant** sucht im Internet nach aufgerufene Dienst. NAchher werden die Dateien local speichern.
- Web-Server und DB-Server laufen auf dem Virtualbox.
- Zugriff auf dem Weboberfläche für Mysql-User ist wie folgt:
- ist via **http://localhost:8080/adminer.php**
! [login] (login.JPG)
! [] (eingeogt.JPG)



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
