# CLAUDE.md — Arbeitsanweisung Astra

## Projektwerte

*Diese Werte stehen **nur hier**. Alle anderen Dateien und Befehle verweisen darauf, statt sie zu wiederholen — genau deshalb, weil Astra zuvor aus Nova geklont wurde und die eingebackenen Nova-Werte monatelang unbemerkt falsch waren.*

| | |
|---|---|
| **Projekt** | Astra |
| **Art der Arbeit** | Blender-NPR-Shader, Analyse und Neuentwicklung |
| **Referenzwerk** | **Arcane** (Animationsserie im League-of-Legends-Universum) |
| **Repo** | `github.com/otterlydommy/astra` (privat) |
| **Arbeitsdatei (Blender)** | *noch keine — `02_Work\` ist leer* |
| **Referenzmaterial** | `01_Input\` (Videodatei, per `.gitignore` ausgeschlossen) |
| **Doku-Ordner** | `.claude\` |
| **Status** | **Noch nicht gestartet.** Die Analyse beginnt erst, wenn Nova abgeschlossen ist und Ressourcen frei sind. |

> ⚙ **Modell:** Aktuell `claude-opus-4-8` (in `.claude\settings.json`). **Wenn die Shader-Analyse startet, auf `claude-fable-5[1m]` umstellen** — Fable ist für die Shader-Arbeit reserviert, wird solange aber nicht verbraucht.

*Wie Dominik generell arbeitet, steht in seinem Profil — lokal automatisch geladen, für Cloud-Sitzungen als `.claude\Person.md` im Repo. Bei Widerspruch gewinnt **diese** Datei.*

---

## ⚠ Offene Altlast aus dem Nova-Klon

Astra wurde ursprünglich als Kopie von Nova angelegt. Die **strukturellen** Dateien sind bereinigt (2026-07-22), zwei **inhaltliche** nicht — denn deren Inhalt ist Dominiks eigener Auftragstext, den Claude nicht erfinden darf:

- **`.claude\7 Phasen Plan.md`** — **eine** Stelle (Abschnitt „Wichtige Einschränkung") nennt noch **Wuthering Waves**. Der Text ist Dominiks Auftragswortlaut und wurde deshalb **nicht** geändert; die Stelle ist mit einer Rückfrage als Kommentar markiert. Der Rest des Plans ist inhaltlich in Ordnung.
- **`.claude\01_Project_Vision.md`** — der Ziel-Look („Messlatte") ist jetzt ausdrücklich `[OFFEN]`. Dort stand ein Nova-Zielbild samt Verweis auf eine nicht existierende Datei; beides entfernt statt sinngemäß übertragen. **Welche Arcane-Szene die Messlatte ist, entscheidet Dominik.** Mehrere Abschnitte sind zudem noch leere Gerüste (Teilziele, Nicht-Ziele, offene Punkte).

**Vor dem Start der Analyse klären.** Bis dahin gilt: Ziel-Look und die genaue Fassung der Einschränkung sind offen — nicht raten.

---

## Ziel

Eine **reproduzierbare, professionelle Blender-Produktionspipeline**, die den Look von **Arcane** möglichst originalgetreu nachbildet. Das Endziel ist ausdrücklich **kein einzelnes Bild**, sondern ein dokumentiertes, wiederverwendbares System aus Shadern, Beleuchtung, Kamera, Rendering, Compositing und Automatisierung.

Astra ist der **zweite Anlauf** nach Nova — dieselbe Arbeitsweise, anderes Referenzwerk. Erkenntnisse aus Nova dürfen als Erfahrung einfließen, aber **keine Nova-Werte, -Pfade oder -Zielbilder** übernommen werden.

---

## Session-Start

1. **BlenderMCP-Verbindung prüfen** (nur lesend: Blender-Version, geladene Datei, Engine). Ohne Verbindung ausdrücklich darauf hinweisen und **keine Live-Aussagen treffen**.
2. Ist-Zustand gegen die Doku prüfen; gemeldet werden **nur Abweichungen** plus Berichtigung.

Ohne Live-MCP-Zugriff jedes Mal ausdrücklich darauf hinweisen, dass die Verbindung wiederhergestellt werden muss.

**Änderungen über MCP nur nach ausdrücklicher Freigabe im Chat** — und nur die konkret freigegebenen.

---

## Arbeitsweise

**Ablauf jeder Aufgabe:** Analyse → Bewertung → Verbesserung → Planung → Umsetzung (nur nach Freigabe) → Validierung → Dokumentation → Commit

Vor jeder Umsetzung: fehlende Informationen klären · Annahmen kennzeichnen · Risiken benennen · Entscheidungen begründen.

> **Keine Vermutungen. Messen statt raten.**

- Große Aufgaben in **logisch abgeschlossene Etappen** teilen; nach jeder Etappe ein Checkpoint, damit ein Abbruch höchstens eine Etappe kostet.
- Ergebnisse **verifizieren**, bevor darauf aufgebaut wird.
- Reproduzierbar und nachvollziehbar arbeiten.
- So einfach wie möglich, so komplex wie nötig.
- Nicht ohne Begründung von bestehenden Architekturen oder Industriestandards abweichen.
- Vorhandene Projektstandards und Werkzeuge nutzen, bevor Neues gebaut wird.
- Vor größeren Architektur- oder Designentscheidungen kritisch auf **Wartbarkeit, Erweiterbarkeit, Performance** und Langzeitwirkung prüfen.

---

## Projektbefehle

- **`/sichern`** — Sitzungsende: Blender speichern, Doku abgleichen, Wiedereinstiegspunkt festschreiben.
- **`/fortsetzen`** — nach Absturz, Nutzungslimit oder neuem Chat: letzten Stand rekonstruieren, Blender-Live gegen Doku abgleichen, weitermachen.
- **`/etappen`** `<Aufgabe>` — große Aufgabe in gesicherten Etappen abarbeiten, mit Checkpoint nach jeder.

---

## Dokumentation

Die Dokumentation ist Bestandteil der Entwicklung, kein nachträglicher Schritt. Sie ist das **Projektgedächtnis** — ein neuer Chat setzt allein darüber fort.

**Vorhanden:** `00_WORKSPACE_RULES.md`, `01_Project_Vision.md`, `7 Phasen Plan.md`

**Entsteht erst mit der Analyse** (noch nicht anlegen, nur wenn Inhalt da ist): Asset-Registry, Shader-Architektur, Progress-Log, Decision-Log, Known-Issues. Namen und Zuschnitt legen wir fest, wenn es soweit ist — **nicht** blind von Nova übernehmen.

Nur **tatsächliche** Änderungen dokumentieren, nichts Geplantes als erledigt.

---

## Versionskontrolle

Astra **ist** ein Git-Repo (seit 2026-07-22). Getrackt wird nur Text: diese Datei, die Doku in `.claude\` und die `.gitignore`. Ausgeschlossen sind `01_Input\` (Referenzvideo, rund 3 GB), Blender-Dateien und `03_export\` — alles über Google Drive gesichert.

**Commit-Pflicht:** Nach jeder abgeschlossenen Änderungsrunde sofort committen, ohne Rückfrage. Nicht bis zum Sitzungsende sammeln. Nachricht kurz und deutsch, benennt **was** und **warum**.

Das ist die einzige Ausnahme von der Freigaberegel. Sie gilt **nicht** für `push`, `reset --hard`, `rebase` oder Löschoperationen.

---

## Sicherheit

- **Referenzdateien in `01_Input\` niemals verändern.**
- Destruktive Änderungen nur nach ausdrücklicher Freigabe, vorher sichern.
- Die Sitzung endet mit einem validierten und dokumentierten Stand.

---

## Rangfolge bei Widersprüchen

**Diese Datei und `00_WORKSPACE_RULES.md` → übrige Projektdoku → Profil → Chatverlauf → Vermutungen**
