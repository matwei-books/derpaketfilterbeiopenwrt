
Was ist OpenWrt?
================

Was ist eigentlich OpenWrt?

Eine gute Frage.
OpenWrt ist eine kleine Linux-Distribution, also ein Betriebssystem für
eingebettete Systeme.
Oder - laut eigener Aussage - ein beschreibbares Dateisystem mit
Paketverwaltung.

Sie bietet ein beschreibbares Dateisystem, einen Paketmanager namens *opkg*
zur Verwaltung der installierten Software und out-of-the-box
Netzwerkunterstützung, einen WLAN-Access-Point, DNS-Service und PPP.
Also fast alles, was man für einen Zugangsrouter braucht.

Was fehlt, kann mit dem bereits erwähnten Paketmanager nachträglich
installiert werden.
Alternativ kann ich mir ein eigenes Firmware-Image für meine Hardware
zusammenstellen, das alle von mir benötigte Software enthält.

Bedienen, das heißt konfigurieren, kann ich es via Telnet, SSH,
Weboberfläche oder X-Windows-System, falls die Hardware ein geeignetes
Display bereitstellt.

> Heutzutage sollte auch der letzte mitbekommen haben, dass es keine gute
> Idee ist Konfigurationsdaten ungeschützt über ein Netzwerk zu schicken.
> Es bleibt in den meisten Fällen als sinnvolle Option für die Konfiguration
> SSH, HTTPS und X-Windows am lokalen Display.

Das OpenWrt-Projekt startete 2004 mit dem "Stable Release".
Diesem folgten die Ausgaben "White Russian" (2007), "Kamikaze" (2007),
"Backfire" (2010), "Attitude Adjustment" (2013), "Barrier Breaker" (2014).

Der aktuelle Entwicklungszweig, genannt "Chaos Calmer", enthält die jeweils
neueste für OpenWrt verfügbare Software.

Da der Entwicklungszweig experimentellen Code enthalten kann, sollte er
nicht für produktive Umgebungen eingesetzt werden.
Dieser Zweig unterstützt zusätzliche Hardware, wird aber als instabil
eingeschätzt und lässt sich manchmal nicht kompilieren.
