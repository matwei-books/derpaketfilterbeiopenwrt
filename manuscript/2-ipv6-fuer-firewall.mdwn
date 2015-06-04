
IPv6 für den Firewall-Administrator
===================================

Mit IPv6 ist 1998 ein weiterer Akteur auf die Bühne der Transport-Protokolle
getreten.
Die Adoption verlief anfangs sehr schleppend, hat in den letzten Jahren aber
an Fahrt aufgenommen.
Inzwischen kann man IPv6 als Firewall-Administrator nicht mehr einfach ignorieren.

Obwohl mittlerweile alle weitverbreiteten Betriebssystem IPv6 ganz gut
unterstützen, ist es noch notwendig IPv6-Projekte vor dem produktiven
Einsatz besonders gründlich zu testen.

Einer der Hauptvorteile von IPv6 ist er riesige Adressraum, der NAT
prinzipiell überflüssig macht.
Was nicht heißen soll, dass es bei IPv6 unmöglich wäre.

Zwar hat man bei IPv6 nicht völlig am grünen Tisch angefangen,, sondern
bewährte Dinge von IPv4 übernommen.
Doch sind etliche Dinge neu hinzugekommen und andere weggefallen.

TCP und UDP verhalten sich hier, wie bei IPv4 gewohnt, daher füge ich dem
dort genannten nichts weiter hinzu als dass UDP bei IPv6 zwingend eine
Prüfsumme berechnen muss, denn der IPv6-Header hat keine Prüfsumme.

Paket-Header
------------

Auch sonst ist der IPv6-Header recht knapp mit 40 Byte, von denen 32 Byte
für die Adressen von Sender und Empfänger draufgehen.
Alle zusätzlich benötigten Informationen gehen in Extension-Header, die
zwischen dem IP-Header und dem Header des höheren Protokolls (zum Beispiel
TCP oder UDP) platziert werden.
Durch Extension-Header kann der IPv6-Header auf maximal 60 Byte anwachsen.

Zur Zeit sind sechs Extension Header spezifiziert, die von allen IPv6-Knoten
unterstützt werden müssen:

*   Hop-by-Hop Options Header, RFC 2460
*   Routing Header, RFC 2460
*   Fragment Header, RFC 2460
*   Destination Options Header, RFC 2460
*   Authentication Header, RFC 4303
*   Encapsulating Security Payload Header, RFC 4303

Es können kein, einer oder mehrere Header in einem IPv6-Paket vorkommen.
Diese werden zwischen dem IPv6-Header und dem Header des Protokolls der
nächsthöheren Schicht platziert.
RFC 2460 gibt eine Reihenfolge vor, die bei mehreren Extension Headern in
einem Datenpaket eingehalten werden soll.
Jeder Header wird durch das Next-Header-Feld des vorherigen identifiziert.
Extension Header werden genau in der Reihenfolge verarbeitet, in der sie im
Datenpaket vorkommen.
Bis auf den Hop-by-Hop Options Header werden die Header nur von den Knoten
mit der Zieladresse verarbeitet.

Adressierung
------------

Aufgrund des riesigen Adressraums und wegen der einfacheren Handhabbarkeit
werden in einer Layer-2-Domain, früher als Broadcast-Domain bezeichnet, 64
Bit als Netzmaske verwendet, so dass 2 hoch 64 Adressen für die Knoten in
diesem Segment verbleiben.

Broadcast selbst wurde abgeschafft und die Funktionen, die Broadcast
verwendeten, müssen nun mit Multicast arbeiten.
Dementsprechend muss jeder IPv6-Knoten Multicast beherrschen.

IGMP, das bei IPv4 für die Verwaltung der Multicast-Gruppen zuständig ist,
entfällt ebenfalls.
Seine Aufgaben nimmt ICMPv6 wahr.

Ebenfalls entfallen ist ARP, mit dem bei IPv4 Ethernet-Adressen und
IP-Adressen verknüpft werden.
Auch diese Aufgaben übernimmt ICMPv6.

Neu gegenüber IPv4 ist Stateless Address Autoconfiguration (SLAAC).
Diese erspart dem Netzwerk-Administrator einiges an Arbeit.
Für IPv4 ist in RFC 3927 ein ähnliches Verfahren beschrieben.

Ebenfalls neu sind die Privacy Extensions bei IPv6, mit denen ein
Client-Rechner in bestimmten Abständen neue Adressen für sich bestimmt und
diese statt der alten Adresse für neue Verbindungen verwendet.
Für Server machen diese Extensions keinen Sinn, denn der Server soll ja
gefunden werden.
Für den Firewall-Administrator bedeutet das, dass er nicht mit festen IP-Adressen
für diese Client-Rechner arbeiten kann, sondern nur mit ganzen
Netzbereichen.
Dem muss er in den Richtlinien Rechnung tragen.

Aber auch Server mit festen IP-Adressen haben immer mehrere Adressen.
So hat jeder IPv6-Knoten mindestens eine link-lokale Adresse an jedem
Interface.
Über diese link-lokalen Adressen kommunizieren die Knoten in einer
Layer-2-Domain und darüber zeigen Router den Netzwerk-Präfix für dieses
Segment an.
Aus diesem Präfix und der link-lokalen Adresse bildet jeder Knoten seine
global eindeutige Adresse.
Damit hat jeder Host schon mindestens zwei Adressen, mit denen er über das
Netz erreicht werden kann.
Hinzu kommen noch einige Multicast-Adressen, auf die er reagieren muss.

Vereinfachungen für Router
--------------------------

Für Router gibt es einige Vereinfachungen bei IPv6.

So können die großen Adressbereiche großzügig an ISPs un deren Kunden
aufgeteilt werden, so dass die Routingtabellen der Core-Router relativ klein
bleiben können.

Router dürfen IPv6-Pakete grundsätzlich nicht fragmentieren.
Ist Fragmentierung notwendig, muss der sendende Host das machen und der
empfangende Host baut das Datagramm wieder zusammen.
Natürlich wird jede DPI-Firewall, die etwas auf sich hält, das auch machen.
Da aber die MTU für IPv6 auf allen Segmenten mindestens 1280 Bytes beträgt,
ist das für eine einfache Firewall nicht nötig, denn im ersten Datagramm
sind alle Informationen für die Entscheidung an Hand der Headerdaten
enthalten.

Gleichzeitiger Betrieb von IPv4 und IPv6
----------------------------------------

Ein Problem für Firewall-Administratoren kann sein, dass auf absehbare Zeit
IPv4 und IPv6 gleichzeitig betrieben werden.
Je nach Anbindung und gewünschter Verbindung kann das eine Protokoll im
anderen getunnelt werden und umgekehrt.

Habe ich eine stabile Verbindung für beide Protokolle kann ich generell alle
Tunnel unterbinden und mit Firewall-Regeln für beide Protokolle arbeiten.

Habe ich nur ein Protokoll von meinem ISP, kann ich selbst einen Tunnel am
Firewall betreiben und dann genauso am Eingang dieses Tunnels filtern.
