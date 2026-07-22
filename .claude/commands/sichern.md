---
description: Projektstand sichern (Session-Ende, Chat-Wechsel oder PC-Shutdown) inkl. Blender-Save
---

Sichere den aktuellen Projektstand von wawa_forge vollständig, damit ein neuer Chat oder ein Neustart ohne Wissensverlust fortsetzen kann:

1. **Blender speichern** (BlenderMCP): `bpy.data.filepath` und `bpy.data.is_dirty` auslesen.
   - Ist `filepath` das Working File (`…\02_Work\carlotta_splashing_summer.blend`) **und** `is_dirty == True`: `bpy.ops.wm.save_mainfile()` ausführen — Dommy hat dafür stehende Freigabe erteilt (D-024). Danach `is_dirty == False` rückprüfen.
   - Ist `filepath` **nicht** das Working File (Referenz, leer, falsches Fenster): **nicht speichern**, Dommy warnen (falsches File geladen).
   - MCP nicht erreichbar: ausdrücklich „Blender-Speicherstand nicht live geprüft" vermerken, mit Schritt 2 fortfahren.
2. **Progress-Log nachziehen:** Sessionverlauf mit `99_claude\01_docs\04_Progress_Log.md` abgleichen; alles noch nicht Dokumentierte als neuen Abschnitt eintragen — nur tatsächliche Änderungen, Messwerte und Entscheidungen, keine Vermutungen.
3. **Restliche Doku abgleichen:** Fehlende Entscheidungen in `05_Decision_Log.md` (fortlaufende D-Nummern), neue/behobene Punkte in `06_Known_Issues.md` (KI-Nummern), Asset-/Textur-Änderungen in `02_Asset_Registry.md`, offene Punkte in `01_Project_Vision.md` §7 nachtragen.
4. **Wiedereinstieg festschreiben:** Den Progress-Log-Eintrag mit einer Zeile `**Wiedereinstieg:** …` abschließen — konkreter nächster Baustein/Schritt, wartende Entscheidungen von Dommy, offene Prüfungen.
5. **Bestätigen:** Kurz zusammenfassen, was gesichert wurde (inkl. Blender-Speicherstatus), und bestätigen, dass ein neuer Chat über den Session-Start-Workflow (CLAUDE.md: MCP-Check → 04_Progress_Log → 06_Known_Issues) nahtlos fortsetzt.
