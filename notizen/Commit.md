---
type: Konzept
---

Ein einzelner Speicherpunkt in [[Git]] — der Moment, in dem du sagst: „Diesen Stand will ich festhalten."

Ein Commit besteht aus drei Dingen: den geänderten Dateien, dem Zeitpunkt samt Urheberin und einer **Nachricht**, die du selbst schreibst. Diese Nachricht ist der Notizzettel am Speicherpunkt:

```
git commit -m "Notizen zum Kundentermin ergänzt"
```

Gute Nachrichten beschreiben das *Warum*, nicht das Offensichtliche. „Änderungen" hilft dir in drei Monaten nicht weiter; „Frontmatter auf OKF umgestellt" schon.

Anders als beim automatischen Speichern in Word entscheidest **du**, wann ein Commit entsteht — deshalb ist der Verlauf keine sinnlose Kette von Zwischenständen, sondern eine lesbare Geschichte deiner Arbeit.

Commits bleiben zunächst nur auf deinem Rechner. Erst ein `push` bringt sie ins [[Repository]] bei [[GitHub]].
