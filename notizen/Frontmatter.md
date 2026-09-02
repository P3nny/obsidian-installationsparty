---
type: Konzept
---

Strukturierte Zusatzinfos am Anfang einer Notiz, zwischen zwei `---`-Linien — getrennt vom eigentlichen Text:

```
---
type: Konzept
status: draft
---
```

Sieht aus wie ein Formularfeld, ist aber ganz normaler Text in der Datei — deshalb können sowohl Menschen als auch Programme (und KI) es lesen und nutzen. Typische Felder: `type` (Art der Notiz), `status` (Reifegrad), `sources` (Herkunft).

Die Schreibweise heißt **YAML**: `schlüssel: wert`, eine Angabe pro Zeile; eingerückte `- `-Zeilen darunter ergeben eine Liste. Mehr Regeln braucht man dafür im Alltag nicht.

In Obsidians Live-Vorschau erscheint Frontmatter als „Eigenschaften"-Block; in der Quellcode-Ansicht siehst du den rohen Text zwischen den `---`-Linien.

Übrigens: Diese Notiz über Frontmatter hat selbst eins — schau oben.
