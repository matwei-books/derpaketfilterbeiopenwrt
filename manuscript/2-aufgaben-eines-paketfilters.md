
Aufgaben eines Paketfilters
===========================

In einem ersten Anlauf, den OpenWrt-Paketfilter zu verstehen, beginne ich
damit, mir klar zu machen, welche Aufgaben ein Paketfilter allgemein zu
erfüllen hat.
Davon ausgehend kann ich die verschiedenen Bestandteile unter diesen
Aspekten betrachten und so vielleicht einige Zusammenhänge besser verstehen.

Allgemein gesprochen ist die Hauptaufgabe eines Paketfilters das Filtern des
Datenverkehrs an Hand von vorgegebenen Regeln für die im Netz vorkommenden
Protokolle.

An Netzwerkgrenzen kann zusätzlich noch die Adressumsetzung,
das heißt das Ändern von Quell- und oder Zieladresse kommen.
Diese findet sich vorwiegend bei IPv4-Netzen, da bei diesen
die Anzahl der frei verfügbaren global eindeutigen Adressen schon seit
längerem nicht mehr den Bedarf decken kann und somit zwei Zwecken dient.
Der eine ist das Verbergen ganzer Netze hinter einzelnen Adressen
(Masquerading), der andere ist das Ermöglichen der Kommunikation von
Rechnern in verschiedenen Netzen, die den gleichen Präfix verwenden.

Kommen wir zurück auf das Filtern des Datenverkehrs, so dient dieses dem
Schutz vor Angreifern im Rahmen der Möglichkeiten eines Paketfilters, die
ich in einem späteren Kapitel genauer beleuchten werde.

Formal dient die Filterung des Datenverkehrs der Durchsetzung einer Policy,
welche den erlaubten und verbotenen Datenverkehr in einem Netzwerk festlegt.
Da die Policy relativ abstrakt die Ziele beschreibt, die ich mit dem
Paketfilter erreichen will, muss ich diese übersetzen in die entsprechenden
Netzwerkadressen und Protokolle.

Die Policy sollte zunächst festlegen, ob ich grundsätzlich alles erlauben
will und nur bestimmten Datenverkehr unterbinden oder ob ich nur bestimmten
Datenverkehr erlauben will und alles andere unterbinden.
Die Antwort hierauf kann in verschiedenen Bereichen unterschiedlich
ausfallen.
Anschließend sollte sie den erlaubten und/oder verbotenen Datenverkehr
beschreiben.

Habe ich eine vollständige Policy, ermittele ich die Protokolle und
Netzwerkadressen, die ich zulassen oder sperren muss.

Eine weitere Aufgabe eines Paketfilters ist der zumindest rudimentäre Schutz
vor Datenabfluss.
Natürlich kann ein Paketfilter nicht davor schützen, dass Daten durch
Ausnutzen der erlaubten Verbindungen das Netz verlassen.
Er kann jedoch mit einer geeigneten Policy den Datenverkehr in Bahnen
lenken, auf denen ich mit anderen Mitteln - Stichwort Data Loss Prevention
beziehungsweise Data Leakage Prevention - dem Abfluss von Daten
entgegenwirken kann.

