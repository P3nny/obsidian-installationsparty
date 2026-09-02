# Workflow: Von der unstrukturierten Notiz zum OKF-Format

## Worum geht's

In Übung 2 aus Teil 1 („Live-Wachstum") hast du `Mein-Eindruck-Workshop.md` angelegt — frei geschrieben, ganz ohne [[Frontmatter]]. Genau so entstehen die meisten Notizen im Alltag: roh, ohne dass man beim Schreiben schon an Struktur denkt. Jetzt übernimmt die KI die Umwandlung ins OKF-Format, statt dass du Frontmatter von Hand tippst.

## Übung: KI bittet um Struktur

Öffne den Plugin-Chat und prompte:

> „Wandle die Notiz `Mein-Eindruck-Workshop.md` ins OKF-Format um. Ergänze im Frontmatter mindestens `type` und `status`. Lass den eigentlichen Text unverändert."

Je nach Plugin bekommst du das Ergebnis entweder direkt in die Datei eingefügt (Button „Anwenden" o. ä.) oder musst es manuell aus dem Chat in die Notiz kopieren.

## Worauf du achten solltest

Claude ist bei strukturierten Aufgaben wie dieser sehr zuverlässig — aber „KI-Ergebnis kurz gegenchecken" ist trotzdem eine gute Grundgewohnheit, unabhängig vom Modell. Wirf einen kurzen Blick auf:

- **Korrekte YAML-Syntax:** drei Bindestriche `---` oben *und* unten
- **Sinnvoller `type`-Wert:** passend zum Inhalt, nicht generisch wie „Notiz"
- **Text unverändert?** Der ursprüngliche Inhalt sollte erhalten geblieben sein

## Erweiterung, falls Zeit bleibt

Bitte die KI, **alle** Notizen im Ordner `03-vaults-und-graph-view/beispiel-notizen` zu überprüfen: Haben alle ein vollständiges Frontmatter? Fehlt irgendwo `type` oder `status`? Zeigt: Dieselbe Fähigkeit skaliert vom Einzelfall auf einen ganzen Vault — genau das macht ein Second Brain mit tausenden Notizen erst praktisch handhabbar.

---

**Weiter geht's in Teil 3:** Jetzt wendest du das Gelernte auf dein eigenes, echtes Wissen an — nicht mehr nur auf die Beispiel-Notizen.
