
IPv4 für den Firewall-Administrator
===================================

IPv4 wird auf längere Zeit noch eine große Rolle spielen.
Dementsprechend werde ich als Firewall-Administrator damit noch häufig
konfrontiert.
In diesem Kapitel gehe ich daher auf wichtige Aspekte dieses und damit
verbundener Protokolle ein.

RFC 791 beschreibt IPv4.
In seinem Header transportiert die folgenden, für den Firewall-Betrieb
relevanten Informationen:

*   ToS (Type of Service)  
    Neben der Standard-Definition in RFC 791 gibt es Ergänzungen für die
    Bedeutung dieses Feldes in den RFCs 2474 (DCSP) und 3168 (ECN).

*   Flags  
    Diese zeigen an, ob das IP-Paket fragmentiert werden darf und
    gegebenenfalls bereits ist.
    Da Fragmentierung absichtlich oder unabsichtlich die Filterung
    erschweren kann, wird man bei einem Paketfilter fragmentierte Pakete
    entweder verwerfen oder zusammenbauen.

*   Protocol  
    Dieses Feld gibt an, welches Protokoll im IP-Datagramm eingebettet ist.
    Seit RFC 3232 führt die IANA eine Online-Datenbank unter
    <http://www.iana.org/>.
    In der Datei */etc/protocols* finden sich die Namen dieser Protokolle
    auf einem Linux-Rechner, wie zum Beispiel 1 für ICMP, 2 für IGMP, 6 für
    TCP und 17 für UDP.
    Will ich am Paketfilter nach Protokollen diskriminieren, muss ich dieses
    Feld beachten.

*   Quell- und Zieladresse mit je 32 Bit dienen in den meisten Regeln als
    Merkmale für die Entscheidung.
    Verwende ich NAT bei der Firewall, muss ich beachten, an welcher Stelle
    im Netfilter-Code die Regel greift und an welcher NAT, um dann entweder
    die originale oder die umgesetzte Adresse zu regulieren.

ICMP
----

ICMP ist für viele Firewall-Administratoren eine Problemzone.
Um 2000 herum brachte Ofir Arkin seine Untersuchungsergebnisse über den
Gebrauch von ICMP für das Scannen von Netzwerken heraus.
Wurden zuvor in den meisten Firewalls ICMP-Pakete freizügig durchgelassen,
so wurden sie danach in vielen Konfiguration rigoros gesperrt.
Leider gibt es einige ICMP-Datagramme, die keinesfalls gesperrt werden
sollen, um den regulären Netzbetrieb nicht zu behindern.
Hier muss ich als Firewall-Administrator sehr gut Bescheid wissen, so dass
ich ICMP in einem eigenen Kapitel bespreche.

TCP
---

Das Transmission Control Protocol, beschrieben in RFC 793 ist eines der
häufigsten Protokolle im Internet.
Es sorgt für eine zuverlässige Verbindung und ist zustandsbehaftet.

Eine TCP-Sitzung wird durch folgende fünf Angaben eindeutig identifiziert:

*   Quell- und Zieladresse sowie das Protokollfeld im IP-Header
*   Quell- und Zielport im TCP-Header

Da TCP-Verbindungen bidirektional sind, können Quell- und Zieladresse sowie
Quell- und Zielport von Datagrammen einer Sitzung paarweise vertauscht sein.

Jede TCP-Sitzung befindet sich in einem Zustand, der für eine Firewall im
TCP-Header zu erkennen ist, an den Flags, der Sequenz- und
Acknowledge-Nummer sowie am Receive-Window.
Bei einer stateless Regel kann die Firewall den Zustand nur an Hand des
aktuellen Datenpakets erraten und entsprechend reagieren.
Es ist bei einer bestehenden Verbindung nicht mehr möglich, zu erkennen,
welche Seite die Verbindung ursprünglich initiiert hatte.
Demgegenüber verfolgt die Firewall bei stateful Regeln die Sitzung und ist
auf diese Weise in der Lage, gefälschte Datenpakete zu erkennen und zu
unterdrücken.
Natürlich braucht das mehr Ressourcen von der Firewall.

TCP enthält einen Mechanismus, mit dem es die maximale Größe von Datagrammen
auf der Verbindungsstrecke ermitteln kann.
Dafür setzt es das *Don't Fragment* Bit im IP-Header und ist darauf
angewiesen, dass ICMP-Unreachable-Pakete zurückkommen können, die dem Sender
sagen, wann ein Datagramm zu groß ist.

Wenn Datenpakete verloren gehen, wiederholt TCP automatisch bereits
gesendete Datagramme.
Diese wiederholt gesendeten Datagramme sollten problemlos durch die Firewall
gehen, wenn die Verbindung legitim ist.
Bei stateful Regeln kann die Firewall Replay-Attacken erkennen, wenn die
Sequenznummer eines Datagramms kleiner ist, als die letzte
Acknowledge-Nummer der Gegenrichtung.

UDP
---

Das Universal Datagram Protocol, beschrieben in RFC 768, ist ein
zustandsloses Protokoll.

Will ich dieses Protokoll mit stateful Regeln überwachen, muss die Firewall
mit Timern arbeiten.
Das bedeutet dementsprechend für die Anwendungen, dass sie regelmäßig Daten
senden müssen, bevor der Timer abläuft, wenn sie den Zustand aktiv halten
wollen.

Eine UDP-Sitzung wird, ähnlich wie eine TCP-Sitzung, durch folgende
Informationen identifiziert:

*   Quell- und Zieladresse sowie Protokollfeld im IP-Header
*   Quell- und Zielport im TCP-Header

Einige auf UDP aufsetzende Protokolle verwenden mehrere dieser eindeutigen
UDP-IDs in einer Sitzung, zum Beispiel TFTP.
Das muss ich als Firewall-Administrator berücksichtigen, wenn diese
Protokolle über die Firewall laufen.

NAT
---

Network Address Translation ist ein Verfahren mit dem man bei IPv4 die
mittlerweile nicht mehr ausreichenden eindeutigen Adressen mehrfach
verwenden kann.
Bei IPv4-Firewalls muss ich jederzeit damit rechnen, mit NAT konfrontiert
zu werden.

Da NAT sehr häufig an Perimeter-Routern eingesetzt wird, bezeichnet man die
beiden Seiten des Routers dementsprechend oft mit *innen* und *außen*.

Es gibt verschiedene Einteilungen von NAT, je nachdem, welchen Aspekt ich
betrachte.
So gibt es NAT bei dem

*   mehrere Adressen eines Netzes auf genau so viele Adressen eines anderen
    Netzes umgesetzt werden, oder

*   mehrere Adressen eines Netzes auf weniger - im Extremfall genau eine -
    Adresse umgesetzt werden.
    Letzteres wird häufig als Masquerading bezeichnet.

Dementsprechend ist es bei NAT im ersten Fall möglich, Verbindungen gezielt
von der äußeren zur inneren Seite aufzubauen, wenn die Adresszuordnung
feststehend ist.

Bei einer Umsetzung von vielen inneren Adressen auf wenige äußere ist es
ohne explizite Konfiguration schwierig, eine Verbindung von außen nach innen
aufzubauen.
Das ist genau dann von Belang, wenn zwei Rechner hinter zwei solchen
NAT-Routern ein direkte Verbindung wünschen, zum Beispiel für VoIP oder
Videokonferenzen
Mittels eines Rendezvous-Server kann einen direkte Verbindung auch ohne
explizite Konfiguration des NAT-Routers aufgebaut werden.

Schließlich behindert NAT IPsec, da letzteres die IP-Adressen authentisiert
und durch das NAT die Datagramme ungültig werden.
Dementsprechend muss man hier auf IPsec hinter NAT ausweichen.

Da das Thema NAT sehr komplex ist und sehr viele Facetten enthält, werde ich
in einem späteren Kapitel noch einmal ausführlich darauf eingehen.

