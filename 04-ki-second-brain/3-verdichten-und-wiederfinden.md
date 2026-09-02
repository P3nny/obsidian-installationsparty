# Verdichten und Wiederfinden

## Worum geht's

Du hast jetzt zwei rohe Sachen im Vault: einen Clip von außen und eine hingekritzelte eigene Notiz. Hier passiert das, was ein Second Brain von einem Ordner voller Dateien unterscheidet.

Der entscheidende Kniff, den Andrej Karpathy so beschreibt: Die KI schreibt und pflegt das Wissensnetz — er selbst fasst es kaum noch direkt an. Aus rohen Quellen entstehen Zusammenfassungen, daraus Begriffsnotizen, daraus Verknüpfungen. Und weil am Ende nur Markdown-Dateien dastehen, braucht es dafür keine Datenbank, keinen Import, kein „Anlernen".[^1]

Vier Bewegungen — probier jede einmal aus.

## 1. Verdichten: aus roh wird strukturiert

Drei getrennte Prompts, damit du jede Fähigkeit einzeln siehst. Nimm dafür `notizen/Rohnotiz-Telefonat-Lotos.md`.

| Prompt an Claudian | Was du beobachten sollst |
|---|---|
| „Ergänze in `Rohnotiz-Telefonat-Lotos.md` ein Frontmatter mit `type` und `status`, passend zum Inhalt. Lass den Text unverändert." | Welchen `type` wählt die KI von sich aus? |
| „Welche bestehenden Notizen im Vault passen inhaltlich dazu? Setz passende `[[...]]`-Links im Text." | Findet sie `Kundenprojekt-Lotos` **und** `Arbeitspräferenzen`? |
| „Diese Notiz enthält zwei verschiedene Gedanken. Trenn sie in zwei Notizen und verlinke sie miteinander." | Erkennt sie, dass die Angebots-Idee nichts mehr mit dem Telefonat zu tun hat? |

**Jetzt nochmal die Graph-Ansicht öffnen.** Der einsame Punkt von eben hängt am Netz. Das ist keine Kosmetik — dazu gleich.

*Der dritte Prompt ist übrigens Luhmanns Prinzip aus Kapitel 1, nur automatisiert: ein Gedanke pro Notiz. Vorher musste man das selbst diszipliniert durchhalten.*

## 2. Verdichten, zweite Stufe: aus einem Clip wird Wissen

Ein 2000-Wörter-Artikel im Vault ist noch kein Wissen, sondern nur ein Text, den du jetzt woanders nicht liest. Nimm einen der Clips aus `Clippings/`:

> „Lies den Clip in `Clippings/` über das Second Brain mit Claude Code. Schreib mir eine Zusammenfassung in fünf Sätzen an den Anfang der Notiz — und leg für die zwei, drei zentralen Begriffe daraus je eine eigene kurze Notiz in `notizen/` an, verlinkt mit dem Clip."

**Worauf du achten kannst:** Danach steht in deinem Vault nicht mehr ein Artikel, sondern ein kleines Netz — Quelle, Zusammenfassung, Begriffe. Genau so wächst so ein System: nicht durch mehr Dateien, sondern durch mehr Verbindungen zwischen ihnen.

### Kurz gegenchecken

Claude ist bei solchen Aufgaben zuverlässig, aber „KI-Ergebnis überfliegen" ist eine gute Grundgewohnheit:

- **YAML-Syntax:** `---` oben *und* unten
- **Sinnvoller `type`:** passend zum Inhalt, nicht generisch „Notiz"
- **Text unverändert?** Deine ursprünglichen Worte sollten noch da sein
- **Keine erfundenen Links:** Zeigen die `[[...]]`-Links auf Notizen, die es wirklich gibt?

*Claudian fragt vor schreibenden Zugriffen nach. Trotzdem gilt: Bevor du eine KI auf einen gewachsenen Vault loslässt, ist ein Backup eine gute Idee — siehe [[Agentische KI]] und das Bonus-Kapitel Git.*

## 3. Wiederfinden: der Chat mit dem eigenen Notizbuch

Warum der ganze Aufwand? Weil eine Notiz nur dann etwas nützt, wenn sie im richtigen Moment gefunden wird.

Ohne Metadaten bleibt der KI nur die Stichwortsuche im Fließtext — und die trifft nur, wenn zufällig dasselbe Wort in der Notiz steht wie in deiner Frage. Wer „Ich mag kein Blattgemüse" notiert hat, bekommt auf „Soll ich Spinat kochen?" trotzdem ein fröhliches Ja.

`type` dreht das um: Die KI kann gezielt *alle Notizen einer Art* heranziehen, statt auf einen Wortzufall zu hoffen. Das Frontmatter ist der Griff, an dem die KI deine Notizen überhaupt anfassen kann.

**Übung — stell diese Fragen:**

> „Was muss ich klären, bevor ich das Angebot für Phase 2 rausschicke?"

> „Zeig mir alle Notizen mit `type: Projekt`, die noch `status: draft` sind."

Die erste Frage braucht mehrere Notizen gleichzeitig (offenes Budget, Hamburg-Standort, deine eigene Regel zum Gegenlesen). Die zweite ist eine Datenbank-Abfrage in normaler Sprache — dafür baust du in Kapitel 5 gleich noch eine Klick-Oberfläche.

## 4. Der Kreislauf schließt sich

Zwei Dinge, die aus einem Notizhaufen erst ein wachsendes System machen:

**Antworten wandern zurück ins Vault.** Wenn die KI etwas Brauchbares herausgearbeitet hat, lass es dort, wo du es wiederfindest:

> „Schreib das Ergebnis als neue Notiz `Offene-Punkte-Lotos-Phase-2.md` und verlink sie mit dem Kundenprojekt."

Damit zahlt jede Frage, die du stellst, aufs Vault ein, statt im Chatverlauf zu versanden.

**Regelmäßig durchputzen lassen.** Was wächst, verwahrlost auch:

> „Prüf alle Notizen im Ordner `notizen`: Wo fehlt `type` oder `status`? Wo widersprechen sich zwei Notizen? Welche zwei Notizen hängen inhaltlich zusammen, sind aber nicht verlinkt?"

Die letzte Frage ist die interessanteste — da schlägt die KI Verbindungen vor, auf die du selbst nicht gekommen wärst. Das ist derselbe Effekt, den Luhmann an seinem Zettelkasten geschätzt hat, nur dass hier jemand anders die Karten durchsieht.

## Der Alltag in drei Zeilen

1. **Roh reinwerfen** — clippen oder hintippen, ohne nachzudenken
2. **Aufräumen lassen** — ab und zu, nicht bei jeder Notiz
3. **Fragen statt suchen** — und die Antwort wieder ablegen

Mehr ist der Kreislauf nicht. Der Unterschied zu einem Ordner voller Dateien liegt nur darin, dass Schritt 2 überhaupt stattfindet — weil ihn niemand mehr von Hand machen muss.

---

**Weiter geht's in Teil 4:** Jetzt läuft derselbe Kreislauf einmal mit deinem eigenen Wissen, nicht mit unseren Beispielen.

[^1]: Andrej Karpathy über seine Arbeitsweise mit LLM-Wissensbasen, X, 2. April 2026. Liegt als Beispiel-Clip in `Clippings/`.
