
Wie weit kann mich ein Paketfilter überhaupt schützen?
======================================================

Um zu verstehen, wie weit und wovor mich ein Paketfilter schützen kann,
greife ich auf das Open Systems Interconnection (OSI) Modell zurück.
Dieses Modell dient seit vielen Jahren als Referenzmodell für
Netzwerkprotokolle.

OSI Modell
----------

Es ist als Schichtenmodell ausgeführt, bei dem jede Schicht genau definierte
Aufgaben hat, die Dienste der tieferliegenden nutzt und seine Dienste den
höherliegenden Schichten zur Verfügung stellt.
Es gibt in diesem Modell die folgenden sieben Schichten:

|   | deutsche Bezeichnung   | englische Bezeichnung |
|---|------------------------|-----------------------|
| 7 | Anwendungsschicht      | application layer     |
| 6 | Darstellungsschicht    | presentation layer    |
| 5 | Sitzungsschicht        | session layer         |
| 4 | Transportschicht       | transport layer       |
| 3 | Vermittlungsschicht    | network layer         |
| 2 | Sicherungsschicht      | data link layer       |
| 1 | Bitübertragungsschicht | physical layer        |

Für das OSI Modell selbst gibt es keine Implementierung, es wird nur für die
Einordnung und den Vergleich realer Protokolle verwendet.
Dabei können reale Protokolle mehrere Schichten des OSI Modells abbilden,
zum Beispiel:

*   Ethernet die Schichten 1 und 2
*   IP, ICMP, IGMP die Schicht 3
*   TCP, UDP die Schicht 4
*   HTTP, SMTP die Schichten 5, 6 und 7

Paketfilter arbeiten nur auf den OSI Schichten 1 bis 4.
Habe ich verschlüsselten Datenverkehr, kann der Paketfilter nur bis zur
Schicht 3, nämlich den IP-Adressen arbeiten.

Application Gateways
--------------------

Für Protokolle der Ebenen 5 bis 7 muss ich entweder auf Application Gateways
für die entsprechenden Protokolle setzen und mit dem Paketfilter erzwingen,
dass diese genutzt werden müssen.
Oder ich untersuche den Datenverkehr mittels Deep Packet Inspection (DPI)
und steuere mit den gewonnenen Erkenntnissen den Paketfilter und damit den
Datenverkehr.

Fail2ban
--------

Eine weitere Möglichkeit besteht darin, die Log-Nachrichten der Server für
Protokolle der höheren Schichten auszuwerten und dementsprechend
unerwünschten Datenverkehr zu unterbinden.
Fail2ban ist ein Beispiel für eine Software, die die Systemprotokolle
auswertet und nach einer bestimmten Anzahl
fehlerhafter Logins die betreffende IP-Adresse über den Paketfilter sperren
kann.
Damit kann ich Brute-Force-Attacken auf Login-Dienste verlangsamen und somit
unbrauchbar machen.
Das funktioniert jedoch nur, wenn der fail2ban-Dämon die benötigten
Log-Nachrichten erhält und der Datenstrom über diesen Rechner läuft.
Für lokale Dienste ist das gegeben.

Port-Knocking und TCP-Stealth
-----------------------------

Weitere Einsatzfälle, bei denen mich Paketfilter schützen, sind
Port-Knocking und TCP-Stealth.
Bei beiden Verfahren unterbindet der Paketfilter zunächst jeglichen
Datenverkehr.
Erst wenn die Software auf dem Server, die den Datenverkehr belauscht, eine
bestimmte Signatur in den Datenpaketen erkennt, veranlasst sie den
Paketfilter, den Datenverkehr zuzulassen.

Damit lassen sich Zugänge zu einem System so verbergen, dass ein Angreifer
den kompletten Datenverkehr des geschützten Systems beobachten und
analysieren müsste, um den geschützten Dienst zu finden und die Signatur zu
ermitteln.
Dieses Verfahren ist sicherer als das nachträgliche Sperren bei
Fehlversuchen, aber nur für einen begrenzten Personenkreis geeignet, den die
entsprechende Signatur bekannt sein und die Software zur Erzeugung der
Signatur zur Verfügung stehen muss.

