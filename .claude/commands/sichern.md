---
description: Projektstand sichern (Sitzungsende, Chat-Wechsel oder Shutdown) inkl. Blender-Save
---

Sichere den aktuellen Projektstand vollständig, damit ein neuer Chat oder ein Neustart ohne Wissensverlust fortsetzen kann.

*Alle projektspezifischen Werte — Arbeitsdatei, Doku-Ordner, Referenzwerk — stehen im **Projektwerte-Block der `CLAUDE.md`**. Von dort holen, nicht aus dieser Datei und nicht aus der Erinnerung.*

## Ablauf

1. **Blender speichern** (über BlenderMCP): `bpy.data.filepath` und `bpy.data.is_dirty` auslesen.
   - Ist `filepath` die **im Projektwerte-Block genannte Arbeitsdatei** *und* `is_dirty == True`: speichern, danach `is_dirty == False` rückprüfen.
   - **Ist im Projektwerte-Block keine Arbeitsdatei eingetragen** (Stand 2026-07-22 der Fall): nicht speichern, sondern Dommy fragen, welche Datei die Arbeitsdatei ist, und den Eintrag ergänzen.
   - Ist `filepath` eine **andere** Datei (Referenz, leer, falsches Fenster): **nicht speichern**, Dommy warnen, dass die falsche Datei geladen ist.
   - MCP nicht erreichbar: ausdrücklich „Blender-Speicherstand nicht live geprüft" vermerken und mit Schritt 2 fortfahren.

2. **Fortschritt nachziehen:** Sitzungsverlauf gegen die Projektdoku abgleichen; alles noch nicht Dokumentierte eintragen. Nur **tatsächliche** Änderungen, Messwerte und Entscheidungen — keine Vermutungen, nichts Geplantes als erledigt.

3. **Restliche Doku abgleichen:** neue Entscheidungen, neue oder behobene Probleme, Asset-/Textur-Änderungen, offene Punkte. Welche Dateien es dafür gibt, steht in der `CLAUDE.md` unter „Dokumentation" — **existiert eine davon noch nicht, erst mit Dommy klären, statt sie blind anzulegen.**

4. **Wiedereinstieg festschreiben:** Den Eintrag mit einer Zeile `**Wiedereinstieg:** …` abschließen — konkreter nächster Schritt, wartende Entscheidungen, offene Prüfungen.

5. **Committen** (Commit-Pflicht, siehe `CLAUDE.md`), dann kurz zusammenfassen, was gesichert wurde — inklusive Blender-Speicherstatus.
