
# Das PC-Wahl Desaster  

Krypto-Basics und wie man es NICHT macht

---

[Auszug aus Präsentation von Linus Neumann ( Sprecher CCC) zur 
Austellungseröffnung „Wahlcomputer“ im Heinz-Nixdorf-Forum 2017](http://www.linus-neumann.de/wp-content/uploads/2017/09/Mit-Papier-und-Bleistift-zur-sicheren-Wahl.mp4)


--- 

Wahl muss: 

* Geheim, frei und gleich
* Transparentes Verfahren und überprüfbare Resultate
* Sicher gegen Manipulation 
* Vertrauenswürdig

--- 

Computer bei Wahlen 

* 1990er Jahre; Forschungsprojekte
* 1999: Erster Einsatz Nedap-Wahlcomputer 
* 2002: Bundesinnenminister kündigt e-Voting für 2006 an 
* bis 2008 ca. 15 Millionen Stimmen an Nedap-Wahlcomputern abgegeben 

---

![Nedap](wahlcomputer-sicher.jpg "Kein Schachcomputer!")

---

![Nedap](wahlcomputer-schachcomputer.png "Jetzt ist er ein Schachcomputer ;)")

---

Verfassungsbeschwerde 

* Gegen Bundestagswahl 2005 
* Keine Möglichkeit zur Prüfung durch den Wähler
* Keine Offenlegung der Systemunterlagen 
* Zweifel an der Sicherheit des Wahlsystems
* Kein Bedarf: sicheres, akzeptiertes Wahlverfahren vorhanden 

---

**Urteil** 

Einsatz war verfassungswidrig

> Beim Einsatz elektronischer Wahlgeräte müssen die wesentlichen Schritte der Wahlbehandlung und Ergebnisermittlung von Bürgern zuverlässig und ohne Sachkenntnis überprüft werden können.

---

![dr-evil](evil/dr-evil.jpeg "Rule 1")

**Rule 1: Computers are evil!**

---

# PC-Wahl

Software zur Organisation, Wahlerfassung und -auswertung von Wahlen. 

---

Alternativen:

* IVU.elect
* Votemanager

--- 

## IVU.elect

getested im Januar 2017 von [Sijmen Ruwhof](https://sijmen.ruwhof.net/weblog/1166-how-to-hack-the-upcoming-dutch-elections)

---

How to hack the upcoming Dutch elections – and how hackers could have hacked all Dutch elections since 2009

---

```
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
```
@[4]
@[6-9]
@[13-14]
@[22-24]
@[1]
@[25]

--- 

# PC-Wahl 

* Bundestagswahl 24. September 2017
* 32 000 000 Stimmen
* 30 Jahre Entwicklung
 
---

Vote IT zu Einsatz der Software PC-Wahl: 

 „in allen Flächenbundesländern bei Kommunalwahlen, Kreiswahlen, Landtagswahlen,
Bundestagswahlen, Europawahlen und Volksabstimmungen eingesetzt.“

---

# Theorie 1

---

**Key Concepts**

* Confidentiality (Vertraulichkeit)
* Integrity (Unversehrtheit)
* Availability (Verfügbarkeit)
* Non-repudiation (Nicht-Abstreitbarkeit)

---

![chain](data/key-concepts.png "chain")

---

**13 Tage bis zur Wahl**

Erstveröffentlichung PC-Wahl-Bericht 

[Thorsten Schröder, Linus Neumann, Martin Tschirsich](https://ccc.de/system/uploads/230/original/PC-Wahl_Bericht_CCC.pdf)

---

![Beißer](evil/Beißer.jpg "Rule 2")

**Rule 2: Security by Obscurity is evil!**

---

# Infrastruktur

---

![infrastruktur](data/infrastruktur.png "infrastruktur")

---

![pcwahl-ftp1](data/pcwahl-ftp1.png "pcwahl-ftp1")

---

![cobra-kai](evil/cobra-kai.jpeg "Rule 3")

**Rule 3: Know your infrastructure, otherwise you could meet evil people!** 

---

![pcwahl-ftp2](data/pcwahl-ftp2.png "pcwahl-ftp2")

---

![pcwahl-ftp3](data/pcwahl-ftp3.png "pcwahl-ftp3")

---

![pcwahl-ftp4](data/pcwahl-ftp4.png "pcwahl-ftp4")

---

![pcwahl-ftp5](data/pcwahl-ftp5.png "pcwahl-ftp5")

---

![darth-vader](evil/darth-vader.jpg "Rule 4")

**Rule 4: Testcode in production is evil!**

---

![ekom21-vpn1](data/ekom21-vpn1.png "ekom21-vpn1")

---

![ekom21-vpn2](data/ekom21-vpn2.png "ekom21-vpn2")

---

![ekom21-vpn3](data/ekom21-vpn3.png "ekom21-vpn3")

---

![ekom21-ftp1](data/ekom21-ftp1.png "ekom21-ftp1")

---

![ekom21-ftp2](data/ekom21-ftp2.png "ekom21-ftp2")

---

![ekom21-ftp3](data/ekom21-ftp3.png "ekom21-ftp3")

---

![blob](evil/The-Blob.jpg "Rule 5")

**Rule 5: Identify and Protect your sensitive Data, otherwise you are evil!**

---

CCC informiert PC-Wahl Team

---

Durchgeführte Aktionen: 

* Dateien mit Endung php werden nicht mehr ausgeführt
* PHP-Skripte nach wie vor auf Server
* FTP-Zugangsdaten wurden geändert 
* CPR-Dateien nur noch nach Eingabe des Passworts möglich 
* AES-Option besteht und "soll" verwendet werden. 

Ab hier keine weiteren Überprüfungen durch ccc möglich.  

---

CCC informiert ekom21

---

Abgeleitete Aktionen: 

* FTP-Modul wird vom öffentlichen Server entfernt
* Einige CPR-Dateien werden entfernt

---

CCC informiert ekom21 über weitere CPR-Dateien 

--- 

geplante Aktionen: 

* Statt FTP soll SFTP zum Einsatz kommen (Entschlüsselung immer noch möglich)
* Statt einem globalen Benutzer, ein Benutzer pro Wahlkreis

---

durchgeführte Aktionen: 

* Umzug von http://wahlinfo.ekom21.de nach Umzug von https://wahlinfo.ekom21.de/wahlen
* FTP-Modul wird wieder öffentlich Bereitgestellt 

---

# Kerckhoffs’ Prinzip

Bereits 1883 postulierte Auguste Kerckhoffs den Verschlüsselungsgrundsatz, dass die
Sicherheit eines Verschlüsselungsverfahrens einzig auf der Geheimhaltung des Schlüssels,
nicht jedoch auf der Geheimhaltung des Verschlüsselungsalgorithmus beruhen soll.

---

![joffrey](evil/joffrey.jpg "Rule 6")

**Rule 6: Hiding your crypto is evil!**

---

# Theorie 2

---

## Hashes und MACs

---

**Salt?**

---

**MD5** 

---

* 128 bit 
* gebrochen

--- 

**SHA-1**

---

* Feb 2005: 2^80 auf 2^69 
* Aug 2005: 2^63 
* Aug 2006: gefälschten Nachricht (derzeit bis zu 25 %)
* ...
* Feb 2017: erste Kollision

---

**SHA-2** 

---

* SHA-224, SHA-256, SHA-384, SHA-512
* gilt als sicher

---

**use SHA-2 (SHA-256) whenever possible**

---

**use procedures like PBKDF2, bcrypt or scrypt for passwords**

---

## Symetrische Verschlüsselung

---

![sym](data/symetrisch.png)

--- 

**RC4**

---

* Weit verbreitet
* gebrochen.

---

**DES**

---

* Weit verbreitet
* 56 Bit 
* Nachfolger: 3DES (schlechte Performance)

---

**Blowfish**

---

* 32-448 Bit 
* Schnell
* Langsame Schlüsselerzeugung

---

**AES**

---

* 128, 192, 256 Bit
* Hohe Effizienz bei Implementierung in Verschlüsselungssoftware oder –hardware
* Sicherheit gegen bekannte kryptografische Angriffe

---

**use AES (AES with 256bit) whenever possible**

---

## Asymetrische Verschlüsselung

---

![gen](data/schluesselgenerierung.png)

---

![aenc](data/verschlüsselung.png)

---

![aenc](data/signierung.png)

---

* Diffie-Hellman
* RSA
* ElGamal
* ECC-Verfahren (Curve25519 ...)
* ...

---

![asym](data/speed-tls.png)

---

**use ECC (Curve25519, ...) or RSA + DH (>2048) whenever possible**

---

## Digitale Signaturen

---

![digsig](data/digitale-signatur.png)

---

## chain of trust

---

### certificate authority

---

![ca](data/ca.jpg)

---

### secure boot

---

## Integrität der Software

Keine Prüfung der Authentizität bei automatischen Update.

---

### MD5-Prüfsummen (24 Tage vor der Wahl)

Im ZIP-Archiv befindet sich jetzt eine MD5-Prüfsummen-Datei

---

### Digitale Signatur (21 Tage vor der Wahl)

studio.exe jetzt signiert mit Comodo-Zertifikat des Herstellers regio iT, wird aber nicht überprüft. 

---

### Digital signierte Installationspakete (13. September 2017)

* Software jetzt eingepackt in "Hello world"-Applikation
* Die Prüfung der Signatur wird vom Nutzer über Appilkation durchgeführt

---

![rabbit](evil/rabbit.jpg "Rule 7")

**Rule 7: roll your own crypto is evil! Use standard tooling.**

---

## Authentizität übertragener Daten

Keine kryptografische Signatur.

---

### GPG-Signaturen

* GPG-Passphrase wird über die Kommandozeile übergeben
* Externes Tool Gpg4win
* Separat installiert

---

```
--passphrase string
 Use string as the passphrase. This can only be used if only one
 passphrase is supplied. Obviously, this is of very questionable
 security on a multi-user system. Don't use this option if you
 can avoid it.

```
---

GPG-Passphrase wird unverschlüsselt gespeichert

* GPG Schlüssel wird in pipe.txt geschrieben
* PC-Wahlserver hat eigenen FTP-Server, der Zugriff auf diese Datei gewährt

---

GPG-Passphrase wird mangelhaft „verschlüsselt“ gespeichert

* GPG-Passphrase wird in datei LOG000.INI gespeichert 
* Eigens entwickelte „Verschlüsselungsroutine“ wird verwendet

---

![trump](evil/donald-trump.jpg "Rule 8")

**Rule 8:  using "Handmade" crypto-alogrithm is very, very evil!**

---

CCC Hacking Tools:

https://github.com/devio/Walruss

CCC Spende: 

https://github.com/devio/Walruss/tree/master/pcw_rsa_donation

---

# Wie gehts jetzt "richtig"?

---

CCC empfiehlt: 

* Einrichtung von mehr als 10.000 Wahllokalen mit Schlüsseln unpraktikabel
* Einsatz einer PKI 
* Einsatz von Smart-Cards (z.B. USB-Stick)
* Verwendung signierter Microsoft-Installer (MSI)
* Einsatz eines eigens erstellten Hersteller Zertifikats 
* Standard-Verfahren

---

![done-right](data/done-right.png "done right")

---