# Workflow: Von der unstrukturierten Notiz zum OKF-Format

## Worum geht's

In Übung 2 aus Teil 1 („Live-Wachstum") hast du `Mein-Eindruck-Workshop.md` angelegt — frei geschrieben, ganz ohne Frontmatter. Genau so entstehen die meisten Notizen im Alltag: roh, ohne dass man beim Schreiben schon an Struktur denkt. Jetzt übernimmt die KI die Umwandlung ins OKF-Format, statt dass du Frontmatter von Hand tippst.

## Übung: KI bittet um Struktur

Öffne den Plugin-Chat und prompte:

> „Wandle die Notiz `Mein-Eindruck-Workshop.md` ins OKF-Format um. Ergänze im Frontmatter mindestens `type` und `status`. Lass den eigentlichen Text unverändert."

Je nach Plugin bekommst du das Ergebnis entweder direkt in die Datei eingefügt (Button „Anwenden" o. ä.) oder musst es manuell aus dem Chat in die Notiz kopieren.

## Worauf du achten solltest — Qualitäts-Check

Kleine lokale Modelle wie unser Llama 3.2 haben nur begrenzte Kapazität, um **gleichzeitig** inhaltlich richtig zu bleiben **und** korrektes YAML-Format einzuhalten — das eine geht leicht auf Kosten des anderen. Prüfe das Ergebnis deshalb auf:

- **Korrekte YAML-Syntax:** drei Bindestriche `---` oben *und* unten, `feld: wert` mit Doppelpunkt und Leerzeichen
- **Sinnvoller `type`-Wert:** nicht generisch wie „Notiz", sondern passend zum Inhalt
- **Text unverändert?** Manchmal kürzt oder verändert ein kleines Modell den ursprünglichen Inhalt versehentlich mit

Falls etwas schiefgeht: nicht schlimm, sondern lehrreich — genau dieser Moment ist der perfekte Vorgeschmack auf Teil 4 (Vergleich der KI-Setups), wo du siehst, wie ein Cloud-Modell wie Claude an derselben Aufgabe abschneidet.

## Erweiterung, falls Zeit bleibt

Bitte die KI, **alle** Notizen im Ordner `02-vaults-und-graph-view/beispiel-notizen` zu überprüfen: Haben alle ein vollständiges Frontmatter? Fehlt irgendwo `type` oder `status`? Zeigt: Dieselbe Fähigkeit skaliert vom Einzelfall auf einen ganzen Vault — genau das macht ein Second Brain mit tausenden Notizen erst praktisch handhabbar.

---

**Weiter geht's in Teil 3:** Jetzt wendest du das Gelernte auf dein eigenes, echtes Wissen an — nicht mehr nur auf die Beispiel-Notizen.
