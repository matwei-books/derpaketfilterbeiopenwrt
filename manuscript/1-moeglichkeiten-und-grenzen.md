
Möglichkeiten und Grenzen des OpenWrt-Paketfilters
==================================================

Der Paketfilter von OpenWrt bietet mir alle Möglichkeiten des Linux
Netfilter-Frameworks.
Ich kann

*   zustandsbehaftete (stateful) und zustandslose (stateless) Firewalls bauen,
*   hoch verfügbare Firewall-Cluster einrichten, wenn die Hardware das
    erlaubt,
*   IP-Adressen mit NAT umsetzen oder mit Masquerading verstecken,
*   Traffic-Shaping mit dem Programm `tc` unterstützen,
*   transparente Proxies und Captive Portals betreiben
*   Datenpakete, insbesondere deren Header, manipulieren.

Natürlich hat ein OpenWrt-Paketfilter auch Grenzen.

Diese ergeben sich zum einen aus der eingesetzten Software durch
Programmfehler und Sicherheitslücken sowie Fehler in der Konfiguration,
mitunter auch durch den Funktionsumfang der bei OpenWrt verfügbaren Software.
Das betrifft auch und vor allem den Kernel.

Zum anderen kann der OpenWrt-Paketfilter an Grenzen stoßen, die sich aus der
Hardware, konkret aus den Peripheriegeräten, dem Hauptspeicher und der CPU
ergeben.

Wie kann ich die Grenzen herausfinden?
--------------------------------------

Die Grenzen der Hardware finde ich durch Lasttests heraus.
Ich sende soviel Traffic zum Gerät wie möglich und beobachte, wie viel davon
durchkommt.
Da ich hier am Paketfilter interessiert bin, kombiniere ich den gesendeten
Traffic aus zulässigen und unzulässigen Datenpaketen um zu sehen, wie weit
letztere die ersteren beeinträchtigen.

Softwarefehler und Sicherheitslücken kann ich durch Penetrationstests
entdecken.
Dabei neue Fehler zu finden erfordert einiges an Erfahrung und meist auch
Einblick in die inneren Abläufe aus dem Quelltext der Software heraus.
Diese Ressourcen haben die wenigsten Anwender von OpenWrt.

Einfacher ist es, Sicherheitsmailinglisten und ähnliche Quellen zu verfolgen
und bei neu entdeckten Schwachstellen zu prüfen, ob mein System dafür
anfällig ist.
Zu diesem Zweck gibt es Exploit-Frameworks, die diese Tests vereinfachen
können.

Wie kann ich die Grenzen verschieben?
-------------------------------------

In manchen Fällen, speziell bei Leistungsproblemen, bleibt mir nur, auf
leistungsfähigere Hardware auszuweichen.
In dringenden Fällen kann ich bestimmte Funktionen abschalten oder den
Durchsatz begrenzen.

Gibt es Workarounds, kann ich diese mindestens temporär nutzen.
Vielleicht sogar selbst welche entwickeln.

Bei Softwareproblemen gibt es mitunter neue Versionen oder Patches, die
das Problem beheben.
Sind diese über die Software-Paketverwaltung erhältlich, brauche ich das
System nur zu aktualisieren.

Gibt es noch keine Version, in der das Problem behoben ist, im Repository,
kann ich die Software selbst übersetzen.
Dafür brauche ich eine Entwicklungsumgebung.

Stärken von OpenWrt
-------------------

Ein großer Vorteil von OpenWrt ist seine Modularität, so dass ich mir ein
System genau nach meinen Wünschen einrichten kann.

Dazu kommt die Paketverwaltung, die mir auch nachträglich erlaubt, mein
System zu erweitern, ohne eine neue Firmware aufspielen zu müssen.

Und schließlich die Vielfalt an billiger Hardware, die unterstützt wird und
damit zu eigenen Experimenten einlädt.

Schwächen von OpenWrt
---------------------

Ein Kritikpunkt ist die Vielzahl von möglichen Erweiterungen in Form von
Softwarepaketen, die gerade Einsteiger verwirren kann.

Je nach vorhandener Hardware ist die Unterstützung verschieden gut.
Vor dem Kauf eines Gerätes ist auf jeden Fall ein Blick in die Liste der
unterstützen Hardware angebracht.

Die Software in den Repositories ist manchmal nicht aktuell genug für einen
bestimmten Einsatzfall.

Wie kann ich die Schwächen kompensieren?
----------------------------------------

Wenn ich sowenig Softwarepakete wie möglich, als nur die für den Einsatz
nötige Software installiere, umgehe ich alle Probleme mit Softwarepaketen,
die nicht auf meinem Gerät sind.
Natürlich muss ich mir trotzdem einen Überblick verschaffen, was vorhanden
ist.
Aber mit der Frage "Brauche ich das wirklich?" kann ich recht schnell
irrelevante Pakete ausschließen und mein System schlanker und sicherer
machen.

Die Hardware kann ich vor dem Einsatz prüfen, ob sie die benötigte Leistung
bringen kann.
Wenn ich sie einsetze ist es unter Umständen vorteilhaft, wenn ich ein Gerät
zusätzlich - als Reserve - besorge, um im Fehlerfall nicht auf andere
Hardware ausweichen zu müssen.
Anderseits kann die Hardware zu einem späteren Zeitpunkt aus zweiter Hand
noch preisgünstiger zu bekommen sein.

Bei Softwareproblemen kann es nötig sein, eine neue Version selbst zu
übersetzen.
Das erfordert dann eine entsprechende Entwicklungsumgebung und Einarbeitung
in dieselbe.
Dafür kann ich dann gleich die Firmware an meine Wünsche anpassen und
brauche nicht nachträglich zusätzliche Software zu installieren.

