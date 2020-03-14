# Platformübergreifende Dienste in ein Netzwerk integrieren
``` 
*-------------------------------------------------------------------------------------------*
| Autor: Hajar Hoseyni                                         Datum: 14.03.2020            |
| Modul: 300 /LB2                                              Repository: hajhos/mym300prj |
| Version: 1                                                                                |
*-------------------------------------------------------------------------------------------*
```
## Inhalt
1. [Einleitung](#Einleitung)
2. [Vorbereitung](#Vorbereitung)
3. [Webserver](#Webserver)
4. [mmdb](#mmdb)
5. [Test](#Test)
6. [Quellen](#Quellen)
___
### Einleitung
Mit diesem Dokument wird man über untenstehende Themen erfahren.
- Ein **Webserver** mit **Vagrant** in einem Netzwerk integrieren.
- Ein **Multi Machine DB** mit Vagrant in einem Netzwerk integrieren.
- Die Dienste auf dem Github-Repository pushen. 
___
### Vorbereitung
- Auf dem **Github** ein neuen Repository erstellen.
- Der Repository auf dem lokalen Speicher clonen.
```
git clone git@github.com:hajhos/mym300prj.git
```
- Auf diesem Verzeichnis **Gitbash** starten.
___
### Webserver
-------------------------------------
! Notebook                            !
! Schulnetz 10.x.x.x (DHCP)           !
! Privates Netz 192.168.55.x (DHCP)   !           
! forwarded_port, guest:80, host:59465!
! memory: 1024                        !
+-------------------------------------+

- Der Webserver-Vagranfile lokal speichern.
- Der Code nach Bedarf anpassen.
 Auf dem 
- Vagrant starten.
``` 
cd c:/Users/hajar/mym300prj 
vagrant up 
```
- Die Weboberfläche auf dem Browser mit der URL http://localhost:59465 aufrufen.
___
### mmdb
___
### Test
___
### Quellen




