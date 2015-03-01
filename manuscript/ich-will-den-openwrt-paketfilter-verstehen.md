
Ich will den OpenWrt-Paketfilter verstehen!
===========================================

Warum?
------

Ich will den Paketfilter verwenden und damit ich ihn optimal verwenden kann,
mmuss ich ihn kennen.

Und ich will ihn verstehen, damit ich darüber schreiben kann und ihn meine
Leser anschließend auch verstehen können.

Warum OpenWrt?
--------------

OpenWrt läuft auf vielen kostengünstigen Geräten mit Netzanschluss.
Einige Firmen verwenden auf OpenWrt basierende Firmware in ihren Geräten.
Freifunk verwendet es, einige andere Projekte auch.
Die Chancen sind also gut, dass OpenWrt bereits an der einen oder anderen
Stelle eingesetzt wird.

Warum nur den Paketfilter und nicht alles?
------------------------------------------

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
Wie man sich die nötigen Informationen selbst beschaffen kann, ist zumindest
teilweise im Anhang beschrieben.

Warum mache ich mir die ganze Mühe?
-----------------------------------

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

Zu diesem Zweck muss ich ein paar Grundlagen wissen, über Netzwerk, Linux
als Betriebssystem und das Netfilter-Framework.
Ich muss in der Lage
sein, meine Ziele klar zu definieren und ich muss ein paar Techniken
beherrschen.
Einmal um meine Ziele umzusetzen und dann, um mich zu vergewissern, dass ich
sie erreicht habe.

