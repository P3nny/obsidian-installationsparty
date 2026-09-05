---
type: Konzept
status: draft
sources: Google Cloud (Ankündigung Juni 2026); Berichterstattung u. a. bei MarkTechPost, Search Engine Journal, MindStudio, Medium, Themenonlab
---

Vertiefung zu [[OKF]]: zwei konkrete Anwendungsfälle, an denen der Nutzen greifbar wird, plus die Abgrenzung zu klassischem RAG.

## Warum das LLMs überhaupt hilft

Ein LLM ist nur so gut wie sein Kontext. In den meisten Organisationen steckt das Wissen, das eine KI bräuchte, verstreut in Datenkatalogen, Wikis, Code-Kommentaren oder in den Köpfen erfahrener Mitarbeiter:innen — jedes neue KI-Tool löst dieses Kontext-Puzzle von vorne. OKF gibt der KI stattdessen kuratiertes, aktuelles Wissen in einer Form, die sie direkt lesen kann, statt zu raten oder zu halluzinieren.

Weil es ein offener Standard ist, gilt das herstellerunabhängig: Ein Wissenspaket, das mit einem LLM erstellt wurde, kann von jedem anderen abgefragt werden — heute Gemini, morgen Claude, ohne Umbau.

## 1. Data Use Cases (Daten)

**Was man organisiert:** Beschreibungen von Tabellen, Kennzahlen-Definitionen, Join-Logik, Datenqualitäts-Hinweise.

**Beispiel:** Eine Firma hat 200 Datenbank-Tabellen. Eine KI soll Fragen beantworten wie „Wie viele aktive Kunden hatten wir letzte Woche?" — ohne Kontext weiß sie nicht, was als „aktiv" zählt, welche Tabelle gemeint ist oder wie man Kunde und Bestellung verknüpft.

Mit OKF gibt es dafür eine Datei `aktive_kunden.md`: Definition („Login in den letzten 30 Tagen"), zuständige Tabelle, Verknüpfungslogik mit anderen Tabellen, bekannte Fallstricke („Testkonten ausschließen!"). Google demonstriert das mit einem Agenten, der ein BigQuery-Dataset durchläuft, für jede Tabelle ein OKF-Dokument entwirft und es mit Zitaten, Schemas und Join-Pfaden anreichert.

**Vorteil:** Die KI schreibt korrekte Abfragen mit den richtigen Geschäftsdefinitionen — konsistent, statt dass jede Anfrage eine Kennzahl anders interpretiert.

## 2. Knowledge Use Cases (Wissen)

**Was man organisiert:** Firmenprozesse, Richtlinien, Produkt-FAQs, Onboarding-Wissen, Projekthistorie — alles, was sonst nur im Kopf erfahrener Kolleg:innen steckt.

**Beispiel:** Eine Datei pro Thema — `urlaubsantrag.md`, `produkt_x_preismodell.md`, `kunde_meier_historie.md`. Kurz, atomar, verlinkt: Die Einträge sind kürzer als ein normaler Wiki-Artikel, mit Metadaten, die der KI helfen, gezielt die richtige Information zu finden.

**Vorteil:** Ein Support-Bot oder interner Assistent antwortet aus geprüftem Wissen statt aus vagen Trainingsdaten. Der Unterschied zu klassischem RAG (Dokumente zerhacken und per Ähnlichkeit durchsuchen): OKF speichert kuratierte, versionierte Concepts, die Agenten direkt lesen **und aktualisieren** können — die KI kann das Wiki also selbst pflegen, und jede Änderung bleibt nachvollziehbar wie bei Code in Git.

## OKF vs. RAG — kein Ersatz, sondern eine Grundlage

RAG beantwortet Fragen; OKF organisiert das Wissen, über das RAG erst sinnvoll suchen kann. Ohne saubere Struktur liefert auch die beste RAG-Pipeline nur Zufallstreffer aus dem Chaos.

## Faustregeln für den Einstieg

- Organisiere Wissen, das stabil, oft gebraucht und geschäftskritisch ist — nicht jeden Chatverlauf
- Eine Datei = ein [[OKF|Concept]], kurz und präzise
- Verlinke großzügig zwischen Dateien
- OKF ist eine frühe, sich noch entwickelnde Spezifikation (aktuell **v0.2**, mit einem eigenen Abschnitt „Changes from v0.1" in der Spec) — für Experimente wie diesen Workshop ideal, für unternehmenskritische Systeme aber noch jung
- Zwei weitere Bausteine kennt die Spec noch: eine optionale `index.md` pro Ordner (Überblick, was dort liegt) und ein optionales `log.md` (Änderungshistorie des Ordners) — Details in [[5-okf-format|Kapitel 4, Teil 5]]

Kurz gesagt: OKF ist die „Bedienungsanleitung deiner Firma" in einem Format, das jede KI versteht — einmal schreiben, überall nutzen.
