# Wissen reinholen: Clippings und Rohnotizen

## Worum geht's

In Teil 1 hast du dein Vault *befragt*. Jetzt die Frage davor: Wie kommt überhaupt etwas rein?

Der Engpass beim Lernen ist selten, gute Inhalte zu finden — sondern die Fleißarbeit danach: zusammenfassen, mit anderem verknüpfen, so ablegen, dass man es wiederfindet. Genau das passiert meistens nicht. Wissen kommt rein, löst kurz etwas aus und verschwindet wieder: verteilt auf 40 offene Browser-Tabs und halb angefangene Notizen, die nie wieder aufgehen.[^1]

Ein Second Brain löst das in zwei Schritten, und beide sind bewusst anspruchslos:

1. **Reinwerfen** — schnell, roh, ohne Struktur (dieser Teil)
2. **Verdichten lassen** — die KI macht daraus strukturiertes Wissen (Teil 3)

Der zweite Schritt ist der Grund, warum der erste so schlampig sein darf.

## Quelle 1: Fremdes Wissen — der Web Clipper

Der **Obsidian Web Clipper** ist eine Browser-Erweiterung von Obsidian selbst. Ein Klick auf einen Artikel — und er landet als saubere Markdown-Notiz in deinem Vault, statt als Tab, den du nie wieder öffnest.

Das Angenehme daran: Der Clipper füllt das [[Frontmatter]] von allein. Woher der Text stammt, wer ihn geschrieben hat, wann er erschienen ist — alles automatisch.

**Schau dir an, was da ankommt:** Im Ordner `Clippings/` liegen zwei fertige Beispiel-Clips. Öffne einen davon und wirf einen Blick auf den Kopf der Datei:

```
---
title: "Building Your Second Brain using Claude Code and Obsidian — Part 1"
source: "https://medium.com/@tom.5610/building-your-second-brain..."
author:
  - "[[Tom Liu]]"
published: 2026-05-06
created: 2026-09-02
tags:
  - "clippings"
---
```

### Kurzer Zwischenstopp: Das ist YAML

Frontmatter wird in einer Notation namens **YAML** geschrieben. Die Regeln, die du dafür brauchst, passen in drei Zeilen:

- `schlüssel: wert` — eine Angabe pro Zeile
- Eingerückte `- ` davor: eine Liste (siehe `tags` oben)
- Der ganze Block steht zwischen zwei `---`-Linien, oben in der Datei

Mehr ist es nicht. Und weil es simpler Text ist, kann eine KI diese Felder genauso lesen wie du — dazu gleich in Teil 3 mehr.

*Bemerkenswert nebenbei: `author` steht dort als `[[Tom Liu]]` — ein Wikilink. Obsidian legt daraus bei Bedarf eine Autoren-Notiz an, an der sich später alles von dieser Person sammelt. Der Clip ist ab Sekunde eins verlinkbar, nicht nur lesbar.*

### Übung: selbst clippen

*Optional — die Erweiterung ist kein Pflicht-Install. Ohne sie arbeitest du einfach mit den zwei Beispiel-Clips in `Clippings/` weiter, alles Folgende funktioniert genauso.*

Installation siehe [[00-installation#Schritt 7b: Web Clipper installieren (optional)|Installation, Teil B, Schritt 7b]].

1. Such dir eine Seite, die dich wirklich interessiert — ein Blogpost, ein Rezept, eine Doku-Seite.
2. Klick auf das Clipper-Symbol im Browser. Du siehst eine Vorschau des Markdowns und die erkannten Eigenschaften.
3. Speichern. Die Notiz liegt danach in deinem Vault unter `Clippings/`.

**Worauf du achten kannst:** Was hat der Clipper an Metadaten erkannt, ohne dass du etwas getippt hast? Und was ist von der Seite *weggefallen* — Werbung, Navigation, Cookie-Banner? Der Clip ist nicht die Seite, er ist ihr Inhalt.

*Tipp: Markierst du vor dem Klicken Text auf der Seite, landet nur dieser Ausschnitt in der Notiz statt des ganzen Artikels.*

## Quelle 2: Eigenes Denken — die Rohnotiz

Ein Second Brain ist kein Lesezeichen-Archiv. Das Wertvollste darin sind die eigenen Gedanken — und die entstehen selten in schöner Form.

**Öffne `notizen/Rohnotiz-Telefonat-Lotos.md`.** So sehen echte Notizen aus: hastig getippt, klein geschrieben, kein Frontmatter, keine Links, mittendrin ein Gedanke, der eigentlich gar nichts mehr mit dem Telefonat zu tun hat.

**Übung:** Öffne die Graph-Ansicht aus Kapitel 3. Die Rohnotiz hängt als einzelner Punkt völlig ohne Verbindung da — obwohl sie inhaltlich klar zu `Kundenprojekt-Lotos` gehört und ein Termin-Thema anspricht, zu dem es längst eine Notiz gibt.

**Das ist der Normalzustand, nicht das Versäumnis.** Wer sich beim Schreiben schon Struktur abverlangt, schreibt irgendwann nichts mehr auf — und genau daran sterben die meisten Notizsysteme. Erfassen muss billig sein.

Teuer ist erst das Aufräumen. Und das machst du ab jetzt nicht mehr selbst.

---

**Weiter geht's in Teil  [[3-verdichten-und-wiederfinden]]:** Claude verdichtet beides — Clipping und Rohnotiz — zu verknüpftem Wissen, und du fragst es danach ab.

[^1]: Tom Liu, „Building Your Second Brain using Claude Code and Obsidian — Part 1", Medium, 6. Mai 2026. Liegt als Beispiel-Clip in `Clippings/`.
