
# Der Paketfilter bei OpenWrt

Ich will den OpenWrt-Paketfilter für Netzwerkdaten verstehen: was er kann,
was er nicht kann, wie ich ihn verwende.
Wofür kann ich ihn einsetzen, wann nehme ich lieber etwas anderes?
Was gibt es anderes?
Welche Vor- und Nachteile hat der OpenWrt-Paketfilter gegenüber anderen
Lösungen?
Welche Vorteile hat OpenWrt insgesamt gegenüber Systemen, die vielleicht
besser als Paketfilter oder Firewall geeignet sind?
Wie kann ich mögliche Schwächen kompensieren?

Damit ich weiß, wovon ich spreche, schaue ich mir die Netzwerkprotokolle an,
um die es geht.
Was muss ich dafür über aktuelle Netzwerkprotokolle wissen?
Welche Fallstricke und Möglichkeiten bietet IPv4?
Was muss ich bei NAT beachten, welche Vorteile bringt es und welche
Nachteile?
Was ist neu an IPv6?
Was ist anders als bei IPv4?
Gibt es andere Protokolle, die ich kennen muss?
Welche Aufgaben haben ICMP und IGMP, wie sind diese bei IPv6 gelöst?
Was passiert, wenn sowohl IPv4 als auch IPv6 gleichzeitig genutzt werden?
Wie geht das überhaupt?
Worauf muss ich vom Standpunkt der Netzwerksicherheit achten?

Nach den Netzwerkprotokollen schaue ich mir das Betriebssystem, den Kernel,
und die Anwenderprogramme als Software-Basis für mein Vorhaben an.
Welche Möglichkeiten bieten mir Linux als Kernel und OpenWrt als
Betriebssystem?
Gibt es andre Betriebssysteme, die ähnliches leisten, andere
Linux-Distributionen?
Wie funktioniert das Netfilter-Framework?
Welche Programme / Softwarepakete gibt es bei OpenWrt, um mit dem
Netfilter-Framework zu arbeiten?
Gibt es andere Paketfilter?

Erst in der Praxis kann ich zeigen, dass meine Überlegungen zur
Filterung von Datenpaketen Hand und Fuß haben.
Wie aber kann ich das erworbene theoretische Wissen in der Praxis überprüfen?
Wie baue ich eine Testumgebung auf?
Mit welchen Programmen kann ich eine Firewall testen?
Wie teste ich die einzelnen Funktionen?
Wie erstelle ich einen Testplan?
Wie erkenne ich, wovor ich mich schützen will?
Wie erkenne ich im laufenden Betrieb, ob das System zuverlässig läuft?
Kann ich IPv4 oder IPv6 Firewalls umgehen?
Wenn ja, wie und worauf muss ich achten, um das zu entdecken und
unterbinden?

Nachdem ich mir Gedanken gemacht habe, wie ich allgemein die
Funktionsfähigkeit eines Paketfilters überprüfen kann, folgen noch ein paar
Überlegungen für reale Projekte mit OpenWrt als Paketfilter.
Wie setze ich mein Wissen in einem realen System um?
Auf welchen Systemen kann ich OpenWrt einsetzen?
Nach welchen Kriterien wähle ich ein System aus?
Wie kann ich die Konfiguration, Dokumentation und Tests einer
Paketfilter-Firewall aus einer Beschreibung generieren?
Wie halte ich das System aktuell?
Wenn Software aktualisiert werden muss und wenn sich meine Anforderungen
ändern.

