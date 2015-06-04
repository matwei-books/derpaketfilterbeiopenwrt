
Alternativen zum OpenWrt-Paketfilter
====================================

Will ich mich nach Alternativen für den Paketfilter von OpenWrt umsehen,
muss ich mir als erstes über den Einsatzzweck und meine Anforderungen klar
sein.

Ist der Paketfilter nur ein relativ kleiner Teil des Gesamtsystems und fiel
die Wahl aus anderen Gründen auf OpenWrt, dann muss der hier vorhandene
Paketfilter reichen.

Bei erhöhten Sicherheitsanforderungen kann es sein, dass ich für die
Netzwerkfilterung auf andere Systeme ausweiche und gegebenenfalls andere
Hardware verwende.

Ein weiterer Aspekt ist das zur Verfügung stehende Budget.
In diesem Punkt ist es allerdings sehr schwierig, eine sinnvolle Alternative
zu OpenWrt zu finden, da dieses nahezu kostenlos zu bekommen ist und auf
sehr billiger Hardware laufen kann.

Ganz anders kann es bei den Vorkenntnissen aussehen.
Wer sich mit dem Paketfilter *pf* von BSD sehr gut auskennt, muss sich
vielleicht erst mit den Eigenheiten der Netfilter-Firewall von Linux
vertraut machen und würde vielleicht ein System mit BSD-Unterbau vorziehen.

Weitere wichtige Punkte sind die Lernbereitschaft desjenigen, der den
Paketfilter einsetzt und die Lernanforderungen des betreffenden Systems.
Gibt es ausreichend geeignete Dokumentation und vielleicht auch
Schulungsmöglichkeiten?
Wie verläuft die Lernkurve beim Einsatz des Systems?
Gibt es anwendbare Beispiele für die wichtigsten Einsatzfälle?

Nicht zu unterschätzen ist der Support für den gewählten Paketfilter.
Habe ich mehrere Systemadministratoren, die die gewählte Technologie
beherrschen, kann ich diesen Punkt enspannter sehen, als wenn ich das System
allein betreue und/oder nicht so sattelfest bin.
Abhängig vom Budget, den Anforderungen und den verfügbaren Vorkenntnissen
wähle ich bezahlten oder Community-Support.
Letzterer funktioniert nur dann wirklich auf Dauer, wenn ich ebenfalls
bereit bin, etwas von meinen Kenntnissen zurückzugeben.

Nachdem ich mir im Klaren über meine Kriterien zur Auswahl einer Alternative
bin, kann ich versuchen, die Spreu vom Weizen zu trennen.

Eine grundlegende Unterteilung der Alternativen ist zwischen propietären und
freien beziehungsweise quelloffenen Systemen.
Bei proprietären Systemen muss ich immer Geld ausgeben, kann in den meisten
Fällen dafür mit einem ordentlichen Support rechnen.
Es bleibt allerdings immer ein gewisser Rest von Unsicherheit, was das
System genau macht.
Quelloffene Systeme bieten demgegenüber prinzipiell die Möglichkeit, das
System bis in die letzte Ecke zu verstehen.
Es ist auch möglich, für quelloffene Systeme und den zugehörigen Support zu
bezahlen.

Die nächste Unterteilung betrifft das eingesetzte Betriebssystem, welches
direkt die Arbeitsweise des Paketfilters bestimmt.
Die wesentlichsten sind

*   Linux mit Netfilter
*   BSD-basierte Systeme mit *pf*
*   proprietäre Systeme

Aufsetzend auf das Betriebssystem finden wir die Konfigurationssoftware, mit
der erst wir den Paketfilter nutzbar machen können.
Hier gibt es

*   Konfiguration über die Kommandozeile beziehungsweise Textdateien,
*   Webbasierte Konfiguration,
*   Zentrale Konfiguration für mehrere Geräte,
*   Konfiguration direkt am Gerät über eingebaute Schalter und Anzeigen.

Die Konfiguration über die Kommandozeile und über Textdateien erfordet eine
genaue Kenntnis der erforderlichen Syntax und hat daher zu Beginn eine
steile Lernkurve.
Auf die Dauer wird diese Lernkurve jedoch kompensiert durch die Möglichkeit,
die Konfiguration in beliebiegen Versionsverwaltungssystemen zu pflegen und
darüber Änderungen zu verfolgen.
Außerdem ist es relativ einfach möglich, die Konfiguration automatisch zu
erzeugen sowie aus der Konfiguration eine verständliche Dokumentation
automatisch zu generieren.

Bei der Konfiguration über Webinterface ist die Lernkurve am Anfang sehr
flach und kleinere Konfigurationsänderungen können relativ schnell
vorgenommen werden.
Dafür sind komplexe Konfigurationen nur mühsam und fehlerträchtig zu
pflegen.
Versionskontrolle ist ohne weiteren Aufwand auch nicht möglich.
Automatisierung über das Webinterface ist zwar möglich, aber sehr aufwendig
und fragil gegenüber Änderungen am Webinterface.

Neben der CLI-/Text-basierten nd der Webkonfiguration ist eine zentrale
Konfiguration mehrerer Paketfilter als Unterscheidungsmerkmal möglich.
Diese bietet die Möglichkeit, mehrere Firewalls in einem Netz aufeinander
abzustimmen.
Einige proprietäre Systeme bieten diese Möglichkeit.
Bei Firewalls mit CLI-/Text-Interface lässt sich diese nachrüsten, auch von
anderen Herstellern.
Bei einem Webinterface würde ich auf Grund der Fragilität davon abraten.

Die letzte Form der Konfiguration ist direkt am Gerät.
Das ist in den meisten Fällen nur für eine minimale Grundkonfiguration
möglich sowie für das Rücksetzen auf Werkseinstellungen.

Bleibt als letztes Unterscheidungsmerkmal für Alternativen die benötigte
Hardware, beziehungsweise das Virtualisierungssystem, falls ich den
Paketfilter in einem Software Defined Network als virtuelle Maschine
betreiben will.

Bei all diesen Unterscheidungsmerkmalen wäge ich die Vor- und Nachteile
gegenüber OpenWrt ab und entscheide mich an Hand meiner Kriterien.


http://en.wikipedia.org/wiki/Comparison_of_firewalls

http://en.wikipedia.org/wiki/List_of_router_and_firewall_distributions

http://www.mondaiji.com/blog/other/it/10175-the-hunt-for-the-ultimate-free-open-source-firewall-distro

http://www.tecmint.com/open-source-security-firewalls-for-linux-systems/


