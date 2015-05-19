
Gleichzeitiger Betrieb von IPv4 und IPv6
========================================

Wenn ich in meinem Netz gleichzeitig IPv4 und IPv6 betreibe, kommen
zusätzliche Herausforderungen auf mich als Firewall-Administrator zu.
Darauf geht dieses Kapitel ein.

Zunächst betrachte ich die möglichen Arten des gleichzeitigen Betriebs von
IPv4 und IPv6.
Das sind die folgenden drei:

*   Dual-Stack-Betrieb, bei dem im Netz und bei den Rechnern beide
    Protokolle gleichzeitig verwendet werden.
*   Tunnel-Techniken, bei denen IPv6-Pakete in IPv4-Paketen transportiert
    werden oder umgekehrt.
*   Netzwerk Adress- und Protokollübersetzung, bei der an einer Stelle im
    Netz IPv4-Pakete in IPv6 umgesetzt werden und umgekehrt.

Dual-Stack-Betrieb
------------------

Dieser erlaubt es, in einem Netzwerk sowohl IPv4 als auch IPv6 gleichzeitig
zu betreiben.

Dual-Stack-Knoten sind Rechner, die beide Protokolle verwenden können.
Diese können in drei verschiedenen Modi arbeiten: nur IPv4, nur IPv6 und
beide Protokolle gleichzeitig.

Bei Dual-Stack-Networks müssen alle Switche, Router und Paketfilter beide
Protokolle unterstützen.

Der Dual-Stack-Betrieb ist einfach zu benutzen und flexibel.
Er ist die beste Option für den gleichzeitigen Betrieb.

Vom Standpunkt der Firewall habe ich zwei Zugänge zum Netzwerk, für die ich
zwei - dem jeweiligen Protokoll angepasste - Sicherheitskonzepte benötige.

Natürlich hat der Dual-Stack-Betrieb auch Nachteile.

So benötigt das Equipment, welches im Dual-Stack-Modus betrieben wird, mehr
RAM und Programmspeicher, da die Funktionen und Status-Informationen für
zwei Protokolle vorgehalten werden müssen.

Ich benötige für beide Protokolle Routing-Informationen und gegebenenfalls
zwei Routing-Protokolle.

Auch die Fehlersuche wird komplizierter, weil ich zusätzlich in Betracht
ziehen muss, das ein Host versucht, einen Dienst mit dem falschen Protokoll
zu erreichen.

Tunnel
------

Beim Tunneln kann ich IPv6-Pakete über IPv4-Netze weiterleiten oder
umgekehrt.

Dabei muss ich drei Elemente betrachten:

*   das Verpacken der Pakete am Eingang des Tunnels,
*   das Auspacken der Pakete am Ausgang des Tunnels und
*   die Verwaltung des Tunnels.

Es gibt manuell und automatisch konfigurierte Tunnel.
Außerdem unterscheidet man Tunnel nach der Art der gekapselten Daten und des
Transports.

Tunnel erlauben es mir genau so von IPv4 zu IPv6 zu migrieren, wie ich es
gerade benötige.
Habe ich kein Dual-Stack-Netzwerk und möchte zwei IPv6-Inseln über ein
IPv4-Netzwerk verbinden, kann ich das sofort machen und muss nicht warten,
bis der Backbone IPv6 übertragen kann.
Ich kann einzelne Hosts oder ganze Netzsegmente umstellen und muss mich
nicht an eine bestimmte Reihenfolge halten.

Natürlich haben auch Tunnel Nachteile.
Sie erzeugen zusätzliche Last auf dem Router, der als Endpunkt für den
Tunnel arbeitet.
Darum sind zustandslose Tunnel vorteilhafter als zustandsbehaftete.

Die Endpunkte des Tunnels benötigen Zeit um die Daten ein- und
auszupacken, wodurch sich die Latenz erhöht.

Selbst wenn die Datenpakete den gleichen Weg nehmen wie ungetunnelte, geht
etwas Bandbreite für die zusätzlichen Kopfdaten des Tunnelprotokolls
verloren.
Durch die zusätzlichen Header verringert sich die MTU des Datenpfades.

Auch die Fehlersuche wird komplexer, da Probleme mit dem Hop-Count, der
Path-MTU und Fragmentierung hinzukommen können.
Bei Problemen mit der Verbindung muss ich sowohl das Tunnelprotokoll als
auch das getunnelte Protokoll untersuchen.

Vom Standpunkt der Sicherheit können insbesondere automatisch aufgebaute
Tunnel problematisch sein, da ich sicherstellen muss, dass auch getunnelte
Daten von einem Paketfilter gefiltert werden, der unter meiner Kontrolle
steht.
Falls durch meinen Paketfilter getunnelte Daten laufen, trage ich dafür
Sorge, dass nur solche getunnelte Daten durchgehen, die von einem
zugelassenen Tunnel-Endpunkt kommen und dass an diesem Endpunkt ebenfalls
gefiltert wird.

Als Firewall-Administrator muss ich mich daher kundig machen, welche Tunnel
in meinem Netzwerk zugelassen und verwendet werden und gegebenenfalls
unerwünschte Tunnel erkennen und sperren.

Nachfolgend zeige ich noch einige gängige Techniken für Tunnel und Quellen
für Informationen dazu.

### 6to4

ist im RFC 3056 beschrieben.

### 6rd (IPv6 Rapid Deployment)

wird in den RFCs 5569 und 5969 beschrieben.

### ISATAP (Intra-Site Automatic Tunnel Addressing Protocol)

ist in RFC 5214 beschrieben.

### Teredo

tunnelt Pakete via UDP und funktioniert damit auch via NAT.
Es ist in RFC 4380 beschrieben.

### Tunnel Broker

sind wie IPv6 Provider für jemand, der nur eine IPv4-Verbindung zum Internet
hat.
Diese sind in RFC 3053 beschrieben.

### GRE (Generic Routing Encapsulation)

erlaubt es, beliebige Protokolle in beliebigen Protokollen zu kapseln.
Es ist in RFC 2784 beschrieben.

Netzwerk Adress- und Protokollumsetzung (NAPT)
----------------------------------------------

Diese setze ich nur ein, wenn keine andere Lösung verfügbar ist und
betrachte sie nur als temporäre Lösung.
Sie unterstützt nicht die fortgeschrittenen Möglichkeiten von IPv6.

Der Vorteil von NAPT ist die damit mögliche "direkte" Kommunikation eines
IPv4-Hosts mit einem IPv6-Hosts.
Bei allen anderen Lösungen müssen beide Rechner das gleiche
Protokoll verwenden.

Nachteile sind limitierte Topologie-Optionen, da ich einen NAPT-Router im
Pfad benötige, der die Protokolle umsetzt.
Anwendungen, die in den Datenpaketen gesendete IP-Adressen verwenden, werden
vermutlich durcheinander kommen.

### Secure Shell (SSH)

erlaubt mit Portweiterleitungen einen verschlüsselten Tunnel für die
Datenpakete und kann dabei das Protokoll umsetzen, wenn der SSH-Rechner im
Dual-Stack-Betrieb arbeitet.

Sicherheitserwägungen
---------------------

Beim gleichzeitigen Betrieb von IPv4 und IPv6 muss ich berücksichtigen, dass
es dann mehrere Zugänge zum Netz gibt, die ich entsprechend meinen
Richtlinien berücksichtigen muss.

Ich muss dafür Sorge tragen, dass Datenpakete, die mein Netzwerk über einen
Tunnel erreichen oder verlassen, ebenfalls gefiltert werden.

RFC 4942 "IP6 Transition / Coexistence Security Considerations" geht auf
dieses Thema ein.

RFC 3964 "Security Considerations for 6to4" geht auf den Tunnelbetrieb ein.

Auch die anderen RFCs zu den verschiedenen Verfahren muss ich studieren,
wenn ich die Verfahren einsetzen will oder erkennen will, ob sie bereits
eingesetzt werden.

