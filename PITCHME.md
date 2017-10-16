
Das PC-Wahl Desaster  
=====================

Krypto-Basics und wie man es NICHT macht

---

Auszug aus Präsentation von Linus Neumann ( Sprecher CCC) zur 
Austellungseröffnung „Wahlcomputer“ im Heinz-Nixdorf-Forum 2017

http://www.linus-neumann.de/wp-content/uploads/2017/09/Mit-Papier-und-Bleistift-zur-sicheren-Wahl.mp4

--- 

Wahl muss: 

* geheim, frei und gleich
* tansparentes Verfahren und überprüfbare Resultate
* sicher gegen Manipulation 
* vertrauenswürdig

--- 

Computer bei Wahlen 

* 1990er Jahre; Forschungsprojekte
* 1999: Erster einsatz Nedap-Wahlcomputer 
* 2002: Bundesinnenminister kündigt e-Voting für 2006 an 
* bis 2008 ca. 15 Millionen Stimen an Nedap-Wahlcomputern abgegeben 

---

![Nedap](wahlcomputer-sicher.jpg "Kein Schachcomputer!")

---

![Nedap](wahlcomputer-schachcomputer.png "Jetzt ist er ein Schachcomputer ;)")


---

Verfassungsbeschwerde 

* gegen Bundestagswahl 2005 
* mangelnde Transparenz 
    * keine Möglichkeit zur Prüfung durch den Wähler
    * keine Offenlegung der Systemunterlagen 

* Zweifel an der Sicherheit des Wahlsystems, insbesondere Wahlgeheimnis und Manipulationsfestigkeit 
* kein Bedarf: sicheres, akzeptiertes Wahlverfahren vorhanden 

---

Urteil 

* Einsatz von Wahlcomputern bei Bundestagswahl 2005 war verfassungswidrig
* Wahl soll nachvollziehbar & begreifbar sein, nicht nur für Techniker, sonder 
  für jeden Bürger


---

>> Beim Einsatz elektronischer Wahlgeräte müssen die wesentlichen Schritte der Wahlbehandlung und Ergebnisermittlung von Bürgern zuverlässig und ohne Sachkenntnis überprüft werden können. <<

---

![the-evil-queen](evil/the-evil-queen.jpg "Rule 1")

Rule 1: Computers are evil! 

---

Was ist PC-Wahl?
=================

Software zur Organisation, Wahlerfassung und -auswertung von Wahlen. 

---

Alternative, ebenfalls in Deutschland eingesetzte Software-Produkte sind:

* IVU.elect
* Votemanager ( heute selbes Unternehmen wie PC-Wahl)

--- 

IVU.elect
-----------

* getested im Januar 2017 von Sijmen Ruwhof 

https://sijmen.ruwhof.net/weblog/1166-how-to-hack-the-upcoming-dutch-elections

---

How to hack the upcoming Dutch elections – and how hackers could have hacked all Dutch elections since 2009

---

Overview of all identified risk
---------------------------------

1. Critical: Optional final paper audit.
2. Very low: Eight internal network shares (from an internal server called Amsterdam) are visible in a YouTube video
3. Medium: The voting-software initial installs a web server on the user’s computer. Users have to open a web browser before they can use the voting-software.
4. High: The voting software-application can be installed on any computer.
5. Medium: The browser for the election software connects to a local host via an unsecured HTTP connection.
6. High: Instructor skips important SHA1 check in YouTube video.
7. High: Voting software allows skipping SHA1 check.
8. High: The insecure, old and deprecated SHA1 hash algorithm is used everywhere in the software.
9. High: The voting software stores voting results in an unencrypted XML file.
10. Medium: PDF file with SHA1 hash code is stored next to corresponding XML file it has to protect.
11. Medium: The voting software / instructor does not mention that PDF files should be printed, nor enforces you to manually delete generated PDF files.
12. Medium: The architect designed the system, but it seems that this person doesn’t review the generated (security) documentation about it.
13. High: Non encrypted USB sticks are used.
14. High: Custom USB sticks can be used and these sticks can be loaded with malicious software.
15. Medium: Web browser automatically completes user passwords on a shared computer.
16. Medium: Instructor uses three letter password.
17. Low: A non personal user account is used.
18. Medium: No password strength policy is in place.
19. Low: The Java session identifier is visible in the internet address.
20. Medium: Instructor uses Windows administrator account instead of low privileged account. The software allows this.
21. Medium: Software saves high integrity XML files into a public location on the computer.
22. High: No automatic SHA1 hash check is in place for XML files stored on the computer.
23. High: Voting results are sent via an unencrypted e-mail over the internet.
24. High: Most sensitive operations in voting software have least SHA1 protection.
25. Etc. etc.

--- 

Bundestagswahl 24. September 2017
=================================== 

---

Vote IT zu Einsatz der Software PC-Wahl: 

 „in allen Flächenbundesländern bei Kommunalwahlen, Kreiswahlen, Landtagswahlen,
Bundestagswahlen, Europawahlen und Volksabstimmungen eingesetzt.“

---

![datenuebermittlung](data/datenuebermittlung.jpg "Datenübermittlung")

---

Security by Obscurity 
----------------------

---

![Beißer](evil/Beißer.jpg "Rule 2")

Rule 2: Security by Obscurity is evil! 

---

07.September 2017 
==================

Erstveröffentlichung PC-Wahl-Bericht durch CCC

https://ccc.de/system/uploads/230/original/PC-Wahl_Bericht_CCC.pdf

---

Upload modifizierter Wahlergebnisse
--------------------------------------

---

* internes VPN Netzwerk
* Upload auf FTP-Server
* FTP-Zugang Passwort-geschützt 


---

Manipulation der Software
--------------------------

---

* Automatische Update Funktion
* Update-Funktion auf allen Systemen gleich

----

Upload modifizierter Ergebnisse an statistische Landesämter
-------------------------------------------------------------

* Übermittlung per XML
* innerhalb von zwei Minuten automatisiert veröffentlicht


---

TODO: Overview

---

Schwachstellen
===============

---

Server wahlauswertung.de des Herstellers von PC-Wahl
-----------------------------------------------------

---

Hosting auf Fremdsystem
------------------------

* 1&1 Shared Host
* 5.507 weitere Kunden

---

![cobra-kai](evil/cobra-kai.jpeg "Rule 3")

Rule 3: Not knowing your infrastructure is evil!

---

Extraktion nicht öffentlicher Datein 
------------------------------------

---

http://www.wahlauswertung.de/phptest/pobs.php

* ausführbar 
* Parameter: Quell- und Zielverzeichnis 
* beliebig ausführbar

---

Schreiben beliebiger Dateien in das Webroot
------------------------------------------

---

weitere php-scripte 

* ausführbar 
* upload-funktion 
* passwort-geschützt: 
  * user: gast, password: test
  * user: test01, password: test01
  * user: test02, password: test02
  * user: gast, password: test

---

![darth-vader](evil/darth-vader.jpg "Rule 4")

** Rule 4: Testcode in production is evil! ** 

---

Mangelhaft gesicherter WebDAV-Zugang
-------------------------------------

---

* www-Benutzer kann Zugangsdaten des Webroots erreichen
* kompletter Zugang zum System 

---

Mangelhaft gesicherter FTP-Zugang
----------------------------------

---

https://www.wahlinfo.de/test/test.zip


* Entschlüsselungsroutine in SmartEditor.exe
* Klartext-Zugangsdaten in entschlüsselten zip
* Benutzername: p8346897
  Passwort: ftppcw7

---

![blob](evil/The-Blob.jpg "Rule 5")

** Rule 5: Identify and Protect your sensitive Data, otherwise you are evil! **

---

CCC informiert PC-Wahl team

Abgeleitete Aktionen: 

* Dateien mit Endung php werden nicht mehr ausgeführt
* php-scripte nach wie vor auf Server
* ftp-Zugangsdaten wurden geändert 

weitere Überprüfungen dadurch nicht mehr möglich. 

---



---

Wie gehts "richtig"?
=====================


https://github.com/devio/Walruss/tree/master/pcw_rsa_donation

---
