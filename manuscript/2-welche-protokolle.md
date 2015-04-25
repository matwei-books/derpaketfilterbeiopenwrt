
Um welche Netzwerk-Protokolle geht es?
======================================

Welche Netzwerkprotokolle sind für mich überhaupt interessant, wenn ich eine
Paketfilter-Firewall betreiben will?
Auf einer Seite gehen Datenpakete hinein, auf der anderen Seite sollen sie
herauskommen oder auch nicht.
Das kann doch gar nicht so viel sein, könnte man meinen.
Es sind erstaunlicherweise recht viele Protokolle, von denen ich mehr wissen
muss, als nur den Namen und wofür es verwendet wird.

Betrachten wir den Bereich IPv4, dan haben wir IPv4 selbst, ICMP, TCP und
UDP als die beiden wohl am häufigsten Protokolle, sowie IGMP.

Bei IPv4 wird für die Zuordnung von Ethernet- und IP-Adressen das
ARP-Protokoll verwendet, von dem ich aber tunlichst die Finger lassen sollte.
Ethernet-Adressen selbst kann ich als Filterkriterium verwenden.
Das Programm, welches die Zuordnung anzeigt, heißt `arp`.

Im Bereich IPv6 muss ich das Protokoll IPv6 selbst und ICMPv6 kennen.
Bei TCP und UDP muss ich nicht viel gegenüber IPv4 dazu lernen.
Die Funktionen von ARP und IGMP übernimmt ICMPv6.

Das wären die wichtigsten Protokolle der OSI-Schichten 1 bis 4.

Die meisten Protokolle der Schichten 5-7 setzen auf TCP oder UDP auf.
Bei diesen muss ich mindestens wissen, welche Ports verwendet werden und
welche Seite die Verbindung aufbaut.

Es gibt unter diesen Protokollen jedoch einige, wie zum Beispiel FTP, die
mit mehr als einer Verbindung arbeiten.
Andere, wie zum Beispiel TFTP verwenden im Laufe einer Sitzung verschiedene
Ports.

Werde ich mit solchen Protokollen konfrontiert, muss ich deren Eigenheiten
genauer kennen.
Für einige dieser Protokolle hilft mir das Connection Tracking Module von
Netfilter, zusammengehörige Datenströme automatisch zu erkennen.

Die meisten Protokolle sind in RFCs beschrieben, die ich im Internet von
<http://tools.ietf.org/> beziehen kann.

Ethernet
--------

Die RFCs 894, 1042 und 2464 beschreiben, wie IPv4 und IPv6 Datenpakete in
Ethernet- und 802.3-Frames eingebettet werden können.
In den meisten Fällen interessieren mich für das Filtern lediglich die
MAC-Adressen.
Arbeitet der Paketfilter jedoch als Ethernet-Bridge und nicht als Router,
kann es interessant sein, sich mit anderen als IP-Protokollen auseinander zu
setzen.

ARP, das Address Resolution Protocol ist in RFC 826 beschrieben, welches in
den RFCs 5227 und 5494 aktualisiert wurde.

IPv4
----

Das Internet Protokoll wurde in RFC 791 beschrieben und in den RFCs 1349,
2474 und 6864 aktualisiert.

ICMP
----

Das Internet Control Message Protocol ist in RFC 792 beschrieben, welches in
den RFCs 950, 4884, 6633 und 6918 aktualisiert wurde.

TCP
---

Das Transmission Control Protocol ist in RFC 793 beschrieben und in den RFCs
1122, 3168, 6093 und 6528 aktualisiert und ergänzt.

UDP
---

Das User Datagram Protocol ist im RFC 768 beschrieben.

IGMP
----

Version 2 des Internet Group Management Protocols ist in RFC 2236
beschrieben, Version 3 in RFC 3376.
RFC 1112 beschreibt die Host Extensions for Multicasting.

IPv6
----

IPv6 wurde erstmals 1995 in RFC 1883 beschrieben.
Diese inzwischen veraltete Beschreibung wurde 1998 durch RFC 2460 abgelöst.
Die RFCs 5095, 5722, 5871, 6437, 6564, 6935, 6946, 7045 und 7112
aktualisieren und ergänzen diesen Draft Standard.


ICMPv6
------

Das Internet Control Message Protocol for IPv6 wurde erstmals 1995 in RFC
1885 beschrieben.
Im Jahr 1998 wurde dieses RFC durch RFC 2463 obsolet, welches selbst wiederum
im Jahr 2006 durch RFC 4443 abgelöst wurde.
RFC 4884 aktualisiert diesen Draft Standard.

