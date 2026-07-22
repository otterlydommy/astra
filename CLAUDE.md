# CLAUDE.md — Astra Workspace

*Allgemeine Arbeitsregeln (Rollen, kritisches Denken, Arbeitsweise, Dokumentationsprinzip, Sicherheit, Kommunikation) stehen in der globalen `C:\Users\Dommy\.claude\CLAUDE.md` und gelten hier zusätzlich. Diese Datei enthält nur noch Astra-Spezifisches.*

---

## Ziel

Eine **reproduzierbare, professionelle Blender-Produktionspipeline**, die den Look der animierten Streaming-Serie **Arcane** (League-of-Legends-Universum) möglichst originalgetreu nachbildet. Das Endziel ist ausdrücklich **kein einzelnes Bild**, sondern ein dokumentiertes, wiederverwendbares System aus Shadern, Beleuchtung, Kamera, Rendering, Compositing und Automatisierung.

---

## Session-Start

1. BlenderMCP-Verbindung prüfen (read-only: Blender-Version, geladene Datei, Engine). Ohne Verbindung ausdrücklich darauf hinweisen und keine Live-Aussagen treffen.
2. Ist-Zustand gegen Doku prüfen; gemeldet werden nur Abweichungen + Berichtigung.

Ohne Live-MCP-Zugriff immer ausdrücklich darauf hinweisen, die Verbindung wiederherzustellen.

**Änderungen über MCP erfolgen ausschließlich nach einer expliziten Freigabe.**

---

## Projektbefehle

- **`/sichern`** — Session-Ende (Chat-Wechsel/Shutdown): speichert Blender (Freigabe D-024), gleicht die Doku ab, schreibt den Wiedereinstiegspunkt.
- **`/fortsetzen`** — nach Absturz/Nutzungslimit/neuem Chat: rekonstruiert den letzten Stand, gleicht Blender-Live gegen Doku ab (auch Halbstände mitten in einer Etappe) und macht weiter.
- **`/etappen`** `<Aufgabe>` — große/lange Aufgabe in gesicherten Etappen abarbeiten; nach jeder Etappe Checkpoint (Blender-Save + Progress-Log), damit ein Abbruch höchstens eine Etappe kostet.

---

## Dokumentation

Nach jeder relevanten Änderung werden die betroffenen Dokumente aktualisiert:

* `02_Asset_Registry.md`
* `03_Shader_Architecture.md`
* `04_Progress_Log.md`
* `05_Decision_Log.md`
* `06_Known_Issues.md`

---

## Workspace-Regeln

Alle dauerhaften Projektregeln stehen in `.claude\00_WORKSPACE_RULES.md`. Diese Regeln sind verbindlich.

---

## Rangfolge bei Widersprüchen

**Diese Datei & Workspace-Regeln → globale `CLAUDE.md` → Chatverlauf → Vermutungen**

Die Dokumentation ist das Projektgedächtnis; ein neuer Chat setzt allein darüber fort.

---

## Hinweis: kein Git-Repository

Astra ist **nicht** unter Versionskontrolle (Stand 2026-07-22). Der Git-Abschnitt der globalen `CLAUDE.md` greift hier also nicht — es gibt kein `git diff`, um Änderungen zu zeigen. Sicherung läuft ausschließlich über Google Drive.
