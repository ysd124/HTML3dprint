# Projektbericht — Interaktive 3D-Druck-Präsentation

**Datei:** `index.html` · **Branch:** `claude/3d-druck-presentation-92x9ys` · **Commit:** `25543cc`
**Online-Version:** https://claude.ai/code/artifact/c00c2ec9-561d-49b6-88e1-6b540cfe2d71

---

## 1. Überblick

Umgesetzt wurde eine vollständige, interaktive Präsentation zum Thema 3D-Druck, die sich
im Browser wie eine PowerPoint-Präsentation bedienen lässt — nicht wie eine Scroll-Website.

| | |
|---|---|
| Umfang | 13 Folien, alle Texte auf Deutsch |
| Format | 16:9, feste Bühne 1600 × 900, auf den Viewport skaliert |
| Dateien | eine einzige `index.html` (~95 KB, 1.923 Zeilen) |
| Enthält | HTML, CSS, JavaScript und 34 selbst gezeichnete SVG-Grafiken |
| Abhängigkeiten | keine — kein Build, kein npm, kein Backend, kein Framework |
| Einzige externe Ressource | Google Fonts (mit System-Fallback, siehe Abschnitt 9) |

Die Datei kann per Doppelklick geöffnet werden und funktioniert sofort.

---

## 2. Aufbau der Präsentation

Die Gliederung folgt eins zu eins der Mindmap; jeder Ast hat eine eigene Folie bekommen.

| Nr. | Titel | Inhalt | Zentrale Grafik |
|----:|-------|--------|-----------------|
| 01 | 3D-Druck | Titel, Untertitel, Schriftfeld wie auf einer technischen Zeichnung | Druckerszene: Bett senkt sich, Bauteil wächst Schicht für Schicht |
| 02 | Was ist 3D-Druck? | digitales Modell, Schicht für Schicht, additive Fertigung, Verfahren | 3D-Modell → Schichten → Bauteil (isometrisch) |
| 03 | Wo wird 3D-Druck eingesetzt? | Schule, Medizin, Industrie, Modellbau, Ersatzteile — je 3 Unterpunkte | fünf Icons im gleichen Strichstil |
| 04 | Vorteile | schnelle Prototypen, wenig Materialverschwendung, leichter Zugang | Versionsreihe V1–V3, subtraktiv vs. additiv, Zugangs-Icons |
| 05 | Nachteile | Dauer, Nachbearbeitung, Materialkosten | Zeitbalken, Bauteil mit Stützstruktur, Spule mit Preisstaffel |
| 06 | Modellieren | Fusion 360, Shapr3D, Tinkercad | Skizze → Volumenkörper → 3D-Modell (STL/3MF) |
| 07 | Druckverfahren | FDM, SLA, SLS mit je 3 Merkmalen und Schichthöhen | drei Verfahrensschemata (Düse, Resin-Becken, Pulverbett) |
| 08 | Vom 3D-Modell zum Druckauftrag | Bambu Studio, OrcaSlicer, PrusaSlicer, wichtigste Parameter | Pipeline Modell → Slicing → Layer → Druckpfad → G-Code |
| 09 | Das richtige Material | PLA, PETG, ABS, TPU, ASA mit Temperaturen und Eigenschaften | Vergleich über 4 Eigenschaftsbalken je Material |
| 10 | Vom Modell zum fertigen Bauteil | die fünf Schritte des Ablaufs | Druckerschiene mit fünf nummerierten Stationen |
| 11 | Vom Rohdruck zum fertigen Teil | Stützen entfernen, entgraten, schleifen, reinigen, lackieren | Rohdruck → Nachbearbeitung → fertiges Bauteil |
| 12 | Beispiel: eine Halterung | kompletter Weg von der Idee bis zum Bauteil, mit Kennwerten | 7-stufige Kette + Datenzeile (Material, Schichthöhe, Infill, Zeit, Gewicht) |
| 13 | Fazit | Zusammenfassung, Schlusssatz „Von der Idee zur ersten Schicht." | Objekt baut sich Schicht für Schicht auf |

Textmenge bewusst knapp gehalten: Stichpunkte statt Fließtext, maximal fünf bis sechs
Punkte pro Bereich. Erklärt wird beim Vortrag, die Folie liefert nur das Gerüst.

---

## 3. Gestaltung

### Farben

Zwei Akzentfarben, und beide haben eine feste Bedeutung — das macht die Grafiken
selbsterklärend, ohne dass eine Legende nötig wäre.

| Rolle | Wert | Verwendung |
|-------|------|------------|
| Hintergrund | `#15181c` | Anthrazit, dazu zwei minimal hellere Stufen für Flächen |
| Text | `#eceff2` / `#a6afb8` / `#727d88` | Off-White, drei Helligkeitsstufen |
| Akzent 1 — Orange | `#ff6a2b` | **physisch**: Filament, Düse, gedrucktes Material, Schichten |
| Akzent 2 — Cyan | `#57c2d6` | **digital**: CAD, Slicer, Maßlinien, Bemaßungen |
| Linien | `#282e35` / `#353d46` | Trennlinien, Rahmen, Hilfslinien |

### Typografie

* **IBM Plex Sans** für Überschriften und Fließtext (300/400/500/600)
* **IBM Plex Mono** für Nummerierungen, Kennwerte, Beschriftungen in Grafiken, Navigation
* Mehr als zwei Schriftfamilien kommen nicht vor.

### Layout

Kein Karten-Design. Getrennt wird ausschließlich über feine 1-px-Linien, wie in einer
technischen Zeichnung — Spalten haben eine Oberlinie, Überschriften eine Grundlinie mit
kurzem orangenem Anschnitt. Jede Folie hat denselben Kopfbereich
(Nummer · Rubrik · Titel · Linie), der Inhalt darunter ist vertikal zentriert.

---

## 4. Animationen und Folienübergänge

Alle Bewegungen sind vom Thema abgeleitet; kein pauschales Ein- und Ausblenden.

| Animation | Wo | Verhalten |
|-----------|----|-----------|
| Schichtaufbau | Folie 01 und 13 | Düse fährt hin und her, Bett senkt sich, Schichten erscheinen einzeln (JavaScript-Schleife) |
| Linien zeichnen | Folien 02, 06, 08, 10 | Pfade werden über `stroke-dasharray` gezeichnet wie bei einer technischen Zeichnung |
| Filamentfluss | Folien 01, 07 | laufende Strichlinie im Schlauch |
| Slicing-Ebene | Folie 08 | Schnittebene wandert langsam durch das Modell |
| Laser-Scan / Lichtquelle | Folie 07 | Scankopf fährt über das Pulverbett, Licht pulsiert unter dem Resin-Becken |
| Aufbau der Inhalte | alle Folien | gestaffeltes Erscheinen von unten, 50–60 ms Versatz |

**Folienwechsel 01 ↔ 02** — der auffällige Übergang: 18 horizontale Bänder wachsen von
unten nach oben ein, abwechselnd von links und von rechts, jedes mit einer dünnen orangenen
Oberkante. Ein Druckkopf fährt an der Kante mit nach oben. Hinter den Bändern wird die Folie
gewechselt, danach geben die Bänder die neue Folie wieder frei. Dauer rund 1,5 Sekunden.

**Alle anderen Folienwechsel** sind bewusst zurückhaltend: die neue Folie wird von unten nach
oben freigegeben (`clip-path`), an der Kante läuft eine dünne orangene Linie mit — die
Druckkante. Dauer 380 ms.

`prefers-reduced-motion` wird ausgewertet: Wer Bewegung reduziert hat, bekommt die Inhalte
ohne Animation und ohne Druck-Transition.

---

## 5. Bedienung

| Eingabe | Wirkung |
|---------|---------|
| `→`, `Leertaste`, `Bild ab`, `Enter` | nächste Folie |
| `←`, `Bild auf` | vorherige Folie |
| `Pos1` / `Ende` | erste / letzte Folie |
| `F` oder Button unten links | Vollbild ein/aus |
| Klick auf rechte / linke Bildhälfte | vor / zurück (praktisch am Beamer) |
| Wischen nach links / rechts | vor / zurück (Tablet, Handy) |
| `index.html#7` | springt direkt zu Folie 7 |

Unten läuft eine Leiste mit „← Zurück", Folienzähler `01 / 13` samt Folienname und
„Weiter →". Am oberen Bildrand zeigt ein dünner Balken den Fortschritt, unterteilt in
13 Abschnitte.

---

## 6. Technik

### Bühne und Skalierung

Die Präsentation zeichnet auf einer festen Fläche von 1600 × 900 px. Diese Bühne wird per
`transform: scale()` auf den verfügbaren Platz skaliert. Dadurch sitzt jedes Element auf
jedem Bildschirm exakt gleich — es gibt keine umbrechenden Layouts und keine bösen
Überraschungen am fremden Beamer. Die Navigationsleiste liegt außerhalb der Bühne und
behält immer ihre gewohnte Größe.

### Codeaufbau

```
index.html
├── <style>
│   ├── 1. Variablen          Farben, Schriften, Abstände, Zeiten
│   ├── 2. Reset & Typografie
│   ├── 3. Bühne & Folien
│   ├── 4. Komponenten        Kopf, Stichpunkte, Spalten, Chips, Balken
│   ├── 5. Grafik-/SVG-Stile  gemeinsame Strichstärken und Farben
│   ├── 6. Folienlayouts
│   ├── 7. Animationen        Keyframes
│   ├── 8. Navigation
│   ├── 9. Folienübergang
│   └── 10./11. Responsive und Ergänzungen
├── <section class="slide"> × 13
├── <footer class="nav">
└── <script>
    ├── 1. Bühne skalieren
    ├── 2. Foliensteuerung
    ├── 3. Druck-Transition
    ├── 4. Tastatur & Touch
    ├── 5. Szenen-Animationen
    └── 6. Fortschrittsanzeige
```

Alle Farben, Abstände, Schriftgrößen und Zeiten stehen als CSS-Variablen im ersten Block —
eine Änderung dort wirkt sich auf die gesamte Präsentation aus.

### Grafiken

Alle 34 Grafiken sind von Hand als SVG geschrieben: Druckerdüse, Druckbett, Filamentrolle,
Schichten, CAD-Würfel, Slicer-Layer, Druckpfad mit Infill, Materialspulen, Stützstrukturen,
Maßlinien, Koordinatensysteme. Keine Stockbilder, keine Icon-Bibliothek. Sie teilen sich
gemeinsame CSS-Klassen für Strichstärke und Farbe und wirken dadurch wie aus einem Guss.

---

## 7. Inhaltliche Angaben und Quellen

Konkrete Zahlen sind auf der jeweiligen Folie eingeordnet und mit einem Hinweis versehen:

| Angabe | Folie | Kennzeichnung |
|--------|-------|---------------|
| Schichthöhe FDM 0,10–0,30 mm | 02 | „Quelle: Standardprofile gängiger Slicer (Bambu Studio, PrusaSlicer)" |
| Druckzeiten ~30 min / ~4 h / 20 h+ | 05 | „Beispielwerte für FDM, 0,2 mm Schichthöhe" |
| Preisstaffel PLA/ABS/TPU | 05 | „Relative Einordnung typischer Filamentpreise" |
| Schichthöhen FDM / SLA | 07 | als Spanne angegeben |
| Düsentemperaturen aller fünf Materialien | 09 | „typische Herstellerangaben, je nach Drucker und Filament abweichend" |
| Eigenschaftsbalken 1–5 | 09 | „qualitative Einordnung" |
| Kennwerte der Beispiel-Halterung | 12 | „Beispielwerte … die tatsächlichen Werte berechnet der Slicer" |

---

## 8. Geprüft

Getestet in Chromium über alle 13 Folien:

* **Layout:** kein vertikaler oder horizontaler Überlauf auf einer der 13 Folien
* **JavaScript:** keine Fehler in der Konsole
* **Navigation:** Vorwärts, Rückwärts, Pos1, Ende, Deeplinks, Druck-Transition
* **Auflösungen:** 1600 × 900, 1280 × 720, 1024 × 768, 820 × 1180 (Tablet), 390 × 844 (Handy)

---

## 9. Bekannte Einschränkungen

1. **Schriften:** IBM Plex wird von Google Fonts geladen. Ohne Internet greift der
   System-Fallback — das Layout hält, die Präsentation sieht nur etwas anders aus.
   Wer sie garantiert offline zeigen will, kann die Schriftdateien lokal einbinden.
2. **Handy im Hochformat:** Bei 16:9 bleibt auf einem schmalen Display naturgemäß wenig
   übrig. Ein dezenter Hinweis „Für die beste Ansicht Gerät drehen" wird eingeblendet.
3. **Vollbild in der eingebetteten Online-Version:** In der eingebetteten Ansicht kann der
   Browser den Vollbildmodus verweigern. Mit der lokalen `index.html` funktioniert er.
4. **Drucken/PDF-Export:** Nicht vorbereitet — es wird immer nur die aktive Folie gedruckt.

---

## 10. Mögliche Erweiterungen

* Referentenansicht mit Notizen in einem zweiten Fenster
* Sprungmarken oder Folienübersicht auf Tastendruck
* PDF-Export als Handout
* Schriften lokal einbetten für den garantiert offlinefähigen Einsatz
