# Vergleich verschiedener KI-Setups

## Worum geht's

Du hast in diesem Kapitel mit Ollama gearbeitet — kostenlos, lokal, aber mit spürbaren Grenzen bei komplexeren Aufgaben. Jetzt schaust du dir an, welche Alternativen es gibt und was sie jeweils kosten — nicht nur in Euro.

## Vergleichstabelle

| Setup | Kosten | Setup-Aufwand | Datenschutz | Stärken |
|---|---|---|---|---|
| **Ollama (lokal)** | kostenlos | mittel (Installation, ~8 GB RAM) | bleibt komplett auf deinem Rechner | gut für einfache Aufgaben, schwächer bei strukturierten Ausgaben |
| **Claude-API + Plugin** | Pay-as-you-go, meist Cent-Bereich | gering (nur Key einfügen) | Daten gehen an Anthropic-Server | zuverlässiger bei komplexen/strukturierten Aufgaben |
| **Claudian + Abo (CLI-Login)** | im bestehenden Abo enthalten | hoch (Node.js, CLI, Login) | Daten gehen an Anthropic-Server | wie Claude-API, aber ohne Zusatzkosten bei vorhandenem Abo |
| **Claude Free im Browser** | kostenlos | keiner (kein Plugin nötig) | Daten gehen an Anthropic-Server, aber nur das, was du manuell reinkopierst | wie Claude-API, aber ohne direkten Vault-Zugriff |

## Übung: Direkter Vergleich

*Nur, wenn du in der Vorbereitung einen Claude-API-Key eingerichtet hast — falls nicht, überspringe diese Übung und lies einfach mit, was andere in deiner Gruppe herausfinden.*

Wechsle im Plugin von Ollama auf Claude als Provider und wiederhole zwei Dinge:

1. Die **OKF-Umwandlung** aus Teil 2 — mit derselben Rohnotiz `Mein-Eindruck-Workshop.md`
2. Die **Multi-Hop-Frage** aus Teil 1 (Zettelkasten ↔ OKF)

Vergleiche beide Ergebnisse nebeneinander — kopiere sie z. B. in zwei separate Notizen oder auf ein Canvas.

**Worauf du achten kannst:** Typischerweise ist die YAML-Formatierung bei Claude zuverlässiger korrekt, und die Multi-Hop-Antwort zieht oft tiefere, unerwartetere Verbindungen. Das ist keine Überraschung — es bestätigt nur konkret erlebt, was wir in Teil 2 schon angekündigt hatten: Ein kleines lokales Modell muss zwischen „inhaltlich richtig" und „formal korrekt" abwägen, ein großes Cloud-Modell hat dafür deutlich mehr Kapazität.

## Übung: Das passende Setup für deine eigene Situation

Denk an deine Antworten aus der Anmeldung (Betriebssystem, Adminrechte, Firmenpolicy) und entscheide:

- Welches der vier Setups würdest du für dich persönlich weiterverwenden?
- Schreib 1–2 Sätze auf, warum — das hilft beim Austausch gleich.

## Austausch in der Breakout-Gruppe

Vergleicht eure Entscheidungen: Wer hat sich für was entschieden, und aus welchem Grund? Gerade bei einer technisch heterogenen Gruppe lohnt sich das — die Senior-Devs unter euch haben oft ganz andere Prioritäten als Einsteigerinnen mit Firmenrechner.

## Zum Abschluss

Wenn du nur einen Satz aus diesem gesamten KI-Kapitel mitnehmen könntest — welcher wäre das? Schreib ihn als letzte Zeile in `Mein-Eindruck-Workshop.md`.

---

*Damit ist Kapitel 5 abgeschlossen. Wer tiefer verstehen will, was hinter dem OKF-Frontmatter steckt, das die KI hier die ganze Zeit genutzt hat, findet die Vertiefung in Kapitel 6.*
