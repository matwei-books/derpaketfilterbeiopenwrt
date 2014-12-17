
# Der Paketfilter bei OpenWrt

## Figuren

* OpenWrt
* Linux-Netfilter (Iptables, Ip6tables, Ebtables)
* IPv4
* IPv6
* Kommandozeilenkonfiguration mit UCI
* Webinterface LuCI
* Testumgebungen
* Hardware

## OpenWrt

OpenWrt ist das Betriebssystem, dass die verwendete Software auf
verschiedensten Rechnern unterstützt.

Das Betriebssystem stellt den Programmen eine definierte Umgebung zur
Verfügung, es verwaltet die Hardwareressourcen und schützt die Programme
voreinander.

Unterschiedliche Programme konkurrieren um die Ressourcen.
Schlechte Programme müssen daran gehindert werden, Schaden anzurichten.
Verschiedene Ziele des Anwenders behindern sich gegenseitig.

Im Laufe des Buches werden Möglichkeiten herausgearbeitet, die verschiedenen
Ziele zu erreichen.

OpenWrt ist das Betriebssystem, dass die verwendeten Programme auf
unterschiedlicher Hardware unterstützt.
Es stellt diesen eine definierte Umgebung zur Verfügung, verwaltet die
Hardware und teilt die Ressourcen den konkurrierenden Programmen zu.
Es hindert schlechte Programme daran, Schaden bei anderen Programmen oder im
Gesamtsystem anzurichten.
Im Verlauf des Buches werden Möglichkeiten herausgearbeitet, wie die
verschiedenen Ziele zu erreichen sind.

## Linux-Netfilter

Netfilter ist das Framework für die Filterung und Manipulation von
Netzwerkpaketen in den Linux-Kerneln ab Version 2.4.

Diese Struktur bietet verschiedene Einsprungspunkte im Netzwerkstack des
Betriebssystems an die Kernel-Module Callback-Funktionen installieren
können, um in die Verarbeitung und Weiterleitung jedes einzelnen Datenpakets
einzugreifen.

Damit ist es möglich, Paketfilter für Firewalls zu realisieren, Adressen
umzusetzen (NAT), transparente Proxies zu realisieren und QoS und
Bandbreitenmanagement auf Linux-Routern einzuführen.

Um die verschiedenen Funktionen des Netfilter-Frameworks zu nutzen, muss man
auf verschiedene Programme für IPv4, IPv6, Bridges und QoS zurückgreifen.

Im Laufe des Buches werden die verschiedenen Bestandteile des
Netfilter-Frameworks vorgestellt.
Welche Programme setze ich wie ein, was kann ich mit ihnen erreichen, wo
liegen die Grenzen?
Welche Programme brauche ich für bestimmte Ziele.

Das Netfilter-Framework sorgt für die Filterung und Manipulation von
Netzwerkdatenpaketen ab Linux-Kernelversion 2.4.
Es bietet verschiedene Einsprungsfunktionen in den Netzwerkstack für
Kernel-Module um in die Verarbeitung und Weiterleitung jedes einzelnen
Datenpakets einzugreifen.
Die Software, die die Funktionen von Netfilter verwendet, wird vorgestellt
und ihr Einsatz erläutert.

## IPv4

IPv4 ist das momentan am häufigsten öffentlich eingesetzte Protokoll zur
Datenübertragung zwischen zwei Rechnern.

Es ist schon sehr lange am Start, es ist etabliert, die meiste Hardware und
Software kann damit umgehen.
Viele Administratoren kennen sich damit aus.
Fast alle Stärken und Schwächen sind bekannt.

Der Adressraum von IPv4 ist zu klein.
Durch NAT, das helfen soll, den Adressraum besser auszunutzen werden die
Administration und einige Protokolle (IPSEC) noch komplizierter.
NAT bricht das Paradigma aus der Anfangszeit des Internet vom "dummen Netz"
und "intelligenten Endgeräten".

Im Laufe des Buches werden einige Fallstricke von IPv4 angesprochen und
Möglichkeiten aufgezeigt, wie man damit umgehen kann.

IPv4 ist das momentan am häufigsten öffentlich eingesetzte Protokoll zur
Datenübertragung.
Es wird schon sehr lange verwendet und ist daher weithin bekannt.
Leider ist sein Adressraum zu klein.
NAT, das helfen soll, den Adressraum besser auszunutzen, bringt seine
eigenen Probleme mit sich.
Insbesondere hebt es das Paradigma vom dummen Netz mit intelligenten
Endgeräten auf.
Im Laufe des Buches werden Fallstricke von IPv4 angesprochen und
Möglichkeiten, damit umzugehen, gezeigt.

## IPv6

IPv6 ist das neue Protokoll für die weltweite Datenübertragung zwischen
Rechnern.

Es will das alte Protokoll IPv4 ablösen.
Es vergrößert den Adressraum, also die Anzahl der verfügbaren Adressen, um
den Faktor 2 hoch 96 (etwa 7 mal 10 hoch 28).
IPv6 entlastet die Router vom Rechenaufwand beim Weiterleiten von
Datenpaketen, weil nicht für jedes Datenpaket eine neue Prüfsumme errechnet
werden muss.

IPv6 ist noch nicht sehr weit verbreitet.
Dementsprechend wird es in unterschiedlichem Grad von den verschiedenen
Geräten unterstützt.
Die Eigenheiten und Fallstricke von IPv6 sind unter Administratoren noch
nicht so gut bekannt, wie bei IPv4.

Im Laufe des Buches werden Grundlagen zum Verständnis von IPv6 angesprochen.

IPv6 ist der vorgesehene Nachfolger von IPv4 für die weltweite
Datenübertragung zwischen Rechnern.
Es vergrößert den Adressraum enorm und löst damit die Adressierungsprobleme
bei IPv4.
Außerdem entlastet es die Router bei der Weiterleitung von Datenpaketen.
Zur Zeit ist IPv6 noch nicht sehr weit verbreitet und wird daher nicht
vollständig von allen Geräten unterstützt.
Auch sind die Administratoren noch nicht so gut mit den Eigenheiten von IPv6
vertraut.

## Kommandozeilenschnittstelle UCI

UCI erlaubt die Konfiguration von OpenWrt über die Kommandozeile.

Es bietet eine einheitliche Syntax für die Konfiguration sämtlicher
installierter Software.
Alle Konfigurationseinstellungen werden in Konfigurationsdateien mit
einheitlicher Syntax abgelegt.
Das bietet den Vorteil, dass der Admin sich nicht an verschiedene Syntax für
die eingesetzte Software gewöhnen muss.

Im Gegenzug muss "neue" Software erst für die Konfiguration via UCI
angepasst werden (bzw. UCI an die neue Software).

Im Laufe des Buches wird die Konfiguration der Paketfilter via UCI
vorgestellt und erläutert.

UCI ist das Programm der Wahl für die Konfiguration eines OpenWrt-Systems
von der Kommandozeile.
Es bietet eine einheitliche Schnittstelle mit einheitlicher Syntax für alle
installierte Software und erleichtert dadurch dem Sysadmin die Arbeit.

## Webinterface LuCI

## Testumgebungen

## Hardware
