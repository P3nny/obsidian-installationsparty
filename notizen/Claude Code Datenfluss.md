---
type: Konzept
sources: https://code.claude.com/docs/en/data-usage
---

Häufige Fragen aus dem Workshop dazu, was eigentlich passiert, wenn Claude über [[Agentische KI|Claudian]] in deinem [[Vault]] liest und schreibt.

## Werden meine Notizen fürs KI-Training verwendet?

**Kommt auf deinen Kontotyp an — kein einheitliches „Nein":**

- **Pro/Max-Abo** (die meisten hier): Anthropic **darf** deine Chats fürs Training nutzen, **wenn** der Schalter unter [claude.ai/settings/data-privacy-controls](https://claude.ai/settings/data-privacy-controls) aktiv ist. Standardmäßig ist das ein Opt-in/Opt-out — kontrollier ihn selbst.
- **API-Key:** grundsätzlich **kein** Training mit deinen Daten, außer du meldest dich aktiv für Anthropics Partnerprogramm an.

Claudian ändert daran nichts — es nutzt im Hintergrund dieselbe Claude Code CLI, dieselben Regeln gelten unverändert.

## Aber die Dateien liegen doch lokal — wieso ist das dann ein Thema?

„Lokal gespeichert" heißt nur: **Die Datei selbst** liegt auf deiner Platte, nicht bei Anthropic. Sobald Claude eine Notiz aber tatsächlich *liest*, um deine Frage zu beantworten, wird ihr Inhalt — verschlüsselt per TLS — an Anthropics Server geschickt. Das ist technisch unvermeidlich: Ein Sprachmodell muss den Text sehen, um damit zu arbeiten.

Was danach mit diesem Inhalt passiert, regelt die Aufbewahrungsfrist deines Kontotyps:

| Kontotyp | Ohne Trainingsfreigabe | Mit Trainingsfreigabe |
|---|---|---|
| Pro/Max | 30 Tage | 5 Jahre |
| API (Standard) | 30 Tage | — |
| Enterprise (Zero Data Retention) | 0 Tage (nur zur Missbrauchsprüfung) | — |

## Warum weiß Obsidian nichts von früheren Chats mit Claude?

Claude Code speichert jede Unterhaltung als eigene Datei unter `~/.claude/projects/…` auf deinem Rechner — im Klartext, aber **außerhalb deines Vaults** und nicht als `.md`-Datei. Obsidian durchsucht ausschließlich den Vault-Ordner; diese Datei sieht es strukturell gar nicht.

Nur was Claude **ausdrücklich in eine Vault-Notiz schreibt** — genau der Second-Brain-Kreislauf aus Kapitel 4 („Schreib das Ergebnis als neue Notiz …") — wird tatsächlich Teil deines Second Brain. Der Rest der Unterhaltung bleibt in dieser separaten Datei und verschwindet für Obsidian im Nichts, sobald die lokale Aufbewahrungsfrist (`cleanupPeriodDays`, standardmäßig 30 Tage) abläuft.

## Kann ich meine Claude-Skills, -Chats oder -Prompts in Obsidian organisieren?

Nicht automatisch — es gibt keine eingebaute Synchronisation zwischen Claude Code und deinem Vault. Was funktioniert: Claude explizit bitten, einen Prompt, ein Skill oder eine Zusammenfassung eines Chats als eigene `.md`-Datei im Vault abzulegen. Danach ist es eine ganz normale Notiz — durchsuchbar, verlinkbar, versionierbar wie jede andere auch.

## Ich will auf eine frühere Session zurückgreifen — geht das?

Ja, dafür gibt es einen eingebauten Weg, ganz ohne Obsidian-Integration:

```
claude --resume
```

(kurz `claude -r`) öffnet eine Auswahlliste aller letzten Sessions **für den aktuellen Projektordner** — mit Pfeiltasten wählen, Enter drücken, weiterarbeiten. `claude --continue` (`claude -c`) macht dasselbe automatisch mit der zuletzt genutzten Session. Beides funktioniert auch als `/resume` innerhalb einer laufenden Session.

Voraussetzung: Du startest Claude aus **demselben Ordner**, in dem die Session ursprünglich lief — bei dir also aus dem Vault-Ordner heraus.

**Wichtige Einschränkung:** `--resume` findet ausschließlich CLI-Sessions (also auch die über Claudian geführten). Chats im **claude.ai-Browser-Tab** sind ein komplett getrenntes System — eigener Verlauf, serverseitig bei Anthropic gespeichert, ohne jede Verbindung zu `~/.claude/projects/`. Eine Brücke zwischen beiden gibt es nicht (die Community fragt bei Anthropic sogar aktiv danach). Genau diese Trennung erlebst du praktisch in Übung 3 aus Kapitel 4, Teil 1.

### Warum nicht einfach `.claude/projects` in den Vault legen?

Naheliegender Gedanke, aber zwei konkrete Probleme sprechen dagegen:

- **Kein lesbares Format:** Jede Session ist eine `.jsonl`-Datei — rohes JSON, eine Zeile pro Ereignis (Werkzeugaufrufe, Nachrichten-Metadaten). In Obsidian geöffnet sieht das nach Datenmüll aus, nicht nach einer Notiz.
- **Datenschutz beim Versionieren:** Wird der Vault über [[Git]] gesichert oder geteilt, würden rohe Chatverläufe (samt Code, Prompts, ggf. sensiblen Inhalten) im Git-Verlauf landen.
- **Maschinengebunden:** Der Ordnername unter `~/.claude/projects/` wird aus dem *absoluten Pfad* deines Vaults gebildet. Synct ihr den Vault auf ein zweites Gerät, ist der Pfad dort anders — die Zuordnung bricht.

### Der Weg, der zur Second-Brain-Philosophie passt

Statt die technische Rohdatei in den Vault zu zwingen: Wenn eine Erkenntnis aus einem Chat dauerhaft bleiben soll, lass Claude sie **explizit als Notiz schreiben** — genau der Kreislauf aus Kapitel 4 („Schreib das Ergebnis als neue Notiz und verlink sie mit …"). Das Ergebnis ist lesbar, durchsuchbar, versionierbar und enthält nur das, was wirklich wertvoll ist, statt der kompletten technischen Unterhaltung. Für den Rest — schnell mal weitermachen, wo man aufgehört hat — reicht `claude --resume`.
