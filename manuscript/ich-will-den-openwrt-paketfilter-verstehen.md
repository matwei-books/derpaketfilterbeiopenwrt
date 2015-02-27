
Ich will den OpenWrt-Paketfilter verstehen!
===========================================

Warum?

Ich will ihn verstehen, damit ich darüber schreiben kann und ihn meine Leser
dann auch verstehen können.

Warum OpenWrt und warum nur den Paketfilter und nicht alles?

Das sind jetzt schon zwei Fragen.

OpenWrt läuft auf vielen kostengünstigen Geräten mit Netzanschluss.
Etliche Projekte verwenden auf OpenWrt basierende Firmware in diesen
Geräten.
Freifunk verwendet es.
Ich erkenne da einen gewissen Bedarf an fundiertem Wissen.

Natürlich kann OpenWrt mehr als nur Pakete zustellen und zu filtern
Aber das soll kein Gesamtwerk über OpenWrt werden, dass mindestens so
schnell veraltet ist, wie geschrieben.
Darum beschränke ich mich auf den Paketfilter und werde hoffentlich
schneller fertig.

Natürlich geht es auch um Themen die einen Paketfilter am Rande tangieren,
um ein grundlegendes Verständnis dieses Paketfilters und ebenso anderer.

In der Tat ist dieses Buch so ausgelegt, dass man den OpenWrt-spezifischen
Teil übergehen kann und den Rest auf andere Linux-Paketfilter anwendet.
Oder man übergeht alles Linux-spezifische und verwendet den Rest um andere
Paketfilter besser zu verstehen.
Wie man sich die dann fehlenden Informationen beschaffen kann, ist zumindest
teilweise im Anhang beschrieben.

Warum mache ich mir die ganze Mühe?

Ein Paketfilter ist ein Werkzeug und die Entwicklung der letzten Jahre hat
mir gezeigt, dass er ein ziemlich wichtiges Werkzeug ist.
Sei es, weil immer mehr Geräte an das Internet angeschlossen werden und dann
wie selbstverständlich "nach Hause" telefonieren.
Sei es dass ich den Schaden durch gehackte Rechner begrenzen will.
Oder einfach nur, weil mit IPv6 der Pseudo-Schutz durch Maskieren der
Adressen wegfällt und ohne Paketfilter alle Geräte in meinem Netz direkt aus
dem Internet erreichbar sind.

Ein Paketfilter ist ein Werkzeug, dass mir bei diesen Problemen helfen kann.
Um den größtmöglichen Nutzen daraus zu ziehen, muss ich mein Werkzeug kennen
und zwar gut.

Das ist das Ziel dieses Buches.
Den Paketfilter von OpenWrt kennenzulernen, um den größtmöglichen Nutzen
daraus zu ziehen.

Damit will ich nicht sagen, dass der Paketfilter von OpenWrt der
bestmögliche ist.
Aber wenn OpenWrt sowieso schon eingesetzt wird, dann will ich auch alles,
was geht, aus den Bordmitteln herausholen und den Paketfilter mit
größtmöglichem Nutzen einsetzen.

Zu diesem Zweck muss ich ein paar Grundlagen wissen, ich muss in der Lage
sein, meine Ziele klar zu definieren und ich muss ein paar Techniken
beherrschen.
Einmal um meine Ziele umzusetzen und dann, um mich zu vergewissern, dass ich
sie erreicht habe.

