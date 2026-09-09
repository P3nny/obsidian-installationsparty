---
type: Konzept
---

KI, die nicht nur **antwortet**, sondern **handelt**. Der Unterschied ist der Sprung von „beschreib mir, wie das geht" zu „mach es".

Ein klassischer Chatbot bekommt Text und gibt Text zurück. Eine agentische KI bekommt zusätzlich **Werkzeuge** — Dateien lesen und schreiben, Ordner durchsuchen, Befehle im [[Terminal]] ausführen — und entscheidet selbst, welche sie in welcher Reihenfolge benutzt, um ein Ziel zu erreichen.

| Frage an die KI                        | Klassischer Chatbot            | Agentisch                                   |
| -------------------------------------- | ------------------------------ | ------------------------------------------- |
| „Wie lege ich eine Notiz an?"          | erklärt es dir                  | erklärt es dir                              |
| „Leg eine Notiz `Test.md` an"          | beschreibt, was du tun müsstest | legt die Datei tatsächlich an               |
| „Prüf alle Notizen auf fehlende Felder" | kann es nicht — kennt sie nicht | liest sie durch und nennt dir die Lücken    |

Genau das macht Claudian in Kapitel 4: Es hat Zugriff auf deinen [[Vault]] und kann darin lesen und schreiben. Deshalb kann es Fragen über *deine* Notizen beantworten, die im Internet nirgends stehen — und Änderungen direkt ausführen, statt sie nur vorzuschlagen.

Die Kehrseite: Was tatsächlich handeln kann, kann auch tatsächlich etwas kaputt machen. Deshalb fragt Claudian vor schreibenden Zugriffen nach — und deshalb ist ein Backup über [[Git]] eine gute Idee, bevor man eine KI auf den ganzen Vault loslässt.

Was genau mit dem passiert, was Claude dabei liest — und wo eigene Chat-Sessions eigentlich landen: [[Claude Code Datenfluss]].
