# Astra — Workspace-Regeln

*Langfristig gültige Regeln dieses Workspaces. Projektwerte (Referenzwerk, Arbeitsdatei, Repo) stehen **nicht hier**, sondern im Projektwerte-Block der `CLAUDE.md` — dort nachsehen.*

---

## Blender

- **Blender 5.2 LTS**
- **BlenderMCP** wird verwendet. MCP bindet an den **Blender-Prozess**, nicht an einzelne Dateien.
- Hardware: NVIDIA GeForce RTX 2070, 8 GB VRAM
- **Render-Engine:** *noch nicht festgelegt.* Nova arbeitet mit EEVEE Next; für Astra ist das **bewusst offen**, weil der Arcane-Look andere Anforderungen stellen kann. Vor der ersten Shader-Arbeit entscheiden und hier eintragen.

## MCP-Disziplin

- Claude arbeitet **standardmäßig ausschließlich lesend** — analysieren, messen, verifizieren, zur Prüfung rendern.
- Änderungen jeder Art über MCP **nur nach ausdrücklicher Freigabe** im Chat, und nur die konkret freigegebenen.
- **Werte setzen und rücklesen in getrennten MCP-Calls.**
- Messen statt raten. Ohne Live-Verbindung ausdrücklich „nicht live geprüft" sagen.

## Designprinzipien

reproduzierbar · modular · wartbar · nachvollziehbar · dokumentiert · möglichst einfach · Debugbarkeit berücksichtigen

## Projektrichtlinien

- Bestehende Systeme erweitern statt ersetzen
- Keine Parallelstrukturen
- Keine Quick-Fixes
- Langfristige Wartbarkeit vor kurzfristiger Geschwindigkeit
- Eigenentwicklung vor dem Kopieren fremder Lösungen
- Änderungen müssen nachvollziehbar dokumentiert werden

## Verhältnis zu Nova

Astra ist der zweite Anlauf nach Nova, mit **anderem Referenzwerk**. Erfahrungen aus Nova dürfen einfließen — **Werte, Pfade, Zielbilder und Entscheidungsnummern jedoch nie.** Astra wurde ursprünglich als Nova-Kopie angelegt; genau daraus entstanden die Fehler, die am 2026-07-22 bereinigt wurden.

**Verweise auf `D-`Nummern, Dateipfade oder Zielbilder aus Nova sind in Astra grundsätzlich ungültig.** Taucht so etwas auf: melden, nicht sinngemäß übertragen.

## Dokumentation

Die Dokumentation ist Bestandteil der Entwicklung und kein nachträglicher Schritt. Sie hat Vorrang vor Chatverläufen und Erinnerungen. Alle Detailregeln liegen in `.claude\`.
