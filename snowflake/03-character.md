
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

## IPv6

## Kommandozeilenschnittstelle UCI

## Webinterface LuCI

## Testumgebungen

## Hardware
