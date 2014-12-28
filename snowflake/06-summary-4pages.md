
# Der Paketfilter bei OpenWrt

Ich will den OpenWrt-Paketfilter für Netzwerkdaten grundlegend verstehen.
Weil ich einsetzen will: zu Hause und im Beruf, wo das sinnvoll ist.

Ich will den OpenWrt-Paketfilter für Netzwerkdaten verstehen: was er kann,
was er nicht kann, wie ich ihn verwende.

Was kann der OpenWrt-Paketfilter?
Wofür kann ich ihn einsetzen?
Was brauche ich, um ihn für verschiedene Zwecke einzusetzen?
Welche Einsatzzwecke sind überhaupt denkbar?

Wo liegen die Grenzen des OpenWrt-Paketfilters?
Wie kann ich diese verschieben?
Wann ist endgültig Schluß, so dass ich lieber etwas anderes nehme?
Was gibt es anderes, dass ich anstelle von OpenWrt nehmen kann, wenn dieses
meine Anforderungen nicht erfüllen kann?

Welche Vor- und Nachteile hat der OpenWrt-Paketfilter gegenüber anderen
Lösungen?
Welche Vorteile hat OpenWrt insgesamt gegenüber Systemen, die vielleicht
besser als Paketfilter oder Firewall geeignet sind?
Welche Schwächen hat es?
Wie kann ich diese Schwächen kompensieren?

Damit ich weiß, wovon ich spreche, schaue ich mir die Netzwerkprotokolle an,
um die es geht.
Mit welchen Netzwerkprotokollen werde ich es zu tun bekommen? (IPv4, IPv6,
TCP, UDP, ICMP, IGMP, OSI-Modell)
Woher bekomme ich weitere Informationen zu diesen?
Was muss ich über diese Protokolle wissen, um eine Firewall sachgerecht zu
betreiben?
Was muss ich bei NAT beachten, welche Vorteile bringt es und welche
Nachteile?
Welche weiteren Protokolle muss ich kennen?

Welche Fallstricke und Möglichkeiten bietet IPv4?
Was ist neu an IPv6?
Was ist anders als bei IPv4?
Welche Aufgaben haben ICMP und IGMP, wie sind diese bei IPv6 gelöst?
Worauf muss ich achten, wenn ich sowohl IPv4 als auch IPv6 gleichzeitig
betreibe?
Wie geht das überhaupt?
Worauf muss ich vom Standpunkt der Netzwerksicherheit achten?

Nach den Netzwerkprotokollen schaue ich mir das Betriebssystem, den Kernel,
und die Anwenderprogramme als Software-Basis für mein Vorhaben an.
Welche Möglichkeiten bieten mir der Linux-Kernel, der bei OpenWrt eingesetzt
wird?
Wie funktioniert das Netfilter-Framework?
Welche Anwendungsprogramme stehen mir bei OpenWrt zur Verfügung?
Woher bekomme ich diese Liste?
Was kann ich mit diesen Programmen machen?
Wie unterstützen sie das Netfilter-Framework des Kernels?
Welche Programme sind noch für mich interessant?
Wie kann ich weitere Software unter OpenWrt verfügbar machen?

Gibt es andere Betriebssysteme, die ähnliches leisten, andere
Linux-Distributionen?

Erst in der Praxis kann ich zeigen, dass meine Überlegungen zur
Filterung von Datenpaketen Hand und Fuß haben.
Wie aber kann ich das erworbene theoretische Wissen in der Praxis überprüfen?
Wie überprüfe ich die Funktionsweise einer Firewall?
Wie baue ich eine Testumgebung auf?
Was benötige ich dafür?
Mit welchen Programmen kann ich eine Firewall testen?
Wie löse ich eine Reaktion aus?
Wie beobachte ich die Reaktion?
Wie teste ich die einzelnen Funktionen?
Welche Funktionen überhaupt?
Wie erstelle ich einen Testplan?
Wie sieht überhaupt ein Testplan aus?

Wie erkenne ich, wovor ich mich schützen will?
Das ergibt sich aus dem Einsatzzweck des Paketfilters.
Welche Angriffe gibt es überhaupt und vor welchen kann mich ein Paketfilter
überhaupt schützen?
Was ist Deep Packet Inspection?
Geht das mit OpenWrt?
Wie erkenne ich im laufenden Betrieb, ob das System zuverlässig läuft?
Kann ich IPv4 oder IPv6 Firewalls umgehen?
Wenn ja, wie und worauf muss ich achten, um das zu entdecken und
unterbinden?

Nachdem ich mir Gedanken gemacht habe, wie ich allgemein die
Funktionsfähigkeit eines Paketfilters überprüfen kann, folgen noch ein paar
Überlegungen für reale Projekte mit OpenWrt als Paketfilter.
Wie setze ich mein Wissen in einem realen System um?
Wie ermittle ich die Anforderungen an meinen Paketfilter?
Auf welchen Systemen kann ich OpenWrt einsetzen?
Nach welchen Kriterien wähle ich ein System aus? (Hardware, Software)
Wie dokumentiere ich das System?
Wie kann ich die Konfiguration, Dokumentation und Tests einer
Paketfilter-Firewall aus einer Beschreibung generieren?
Wie halte ich das System aktuell?
Wie erweitere ich das System, wenn sich die Anforderungen ändern?

