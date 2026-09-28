# Report – Präsentation „Digitale Medien: E-Mail & Podcast“

## Überblick

| | |
|---|---|
| Datei | `index.html` (eine einzige Datei, direkt im Browser startbar) |
| Technik | HTML + CSS + JavaScript, keine externen Bibliotheken, Bilder oder Schriften |
| Folien | 4 |
| Format | feste 16:9-Bühne (1920 × 1080), wird auf jeden Bildschirm skaliert |
| Sprache | Deutsch |

## Folien

### 01 – Einleitung
- **Text:** „Digitale Medien“, darunter „E-Mail & Podcast“, dazu zwei kurze Beschriftungen („klassische digitale Kommunikation“, „modernes Audio-Medium“).
- **Visuell:** Ein blauer Briefumschlag zeichnet sich. Aus ihm läuft eine Linie nach rechts, die sich in eine orange Audio-Wellenform verwandelt und danach ruhig weiterschwingt.
- **Aufbau:** Die Grafik bildet den Mittelpunkt, der Titel steht groß unten links.

### 02 – E-Mail
- **Links:** ein schlichtes Mail-Fenster mit „An“, „Betreff“, angedeuteten Textzeilen, Anhang „Dokument.pdf“ und Senden-Knopf.
- **Animation:** Die Textzeilen bauen sich auf, „Senden“ wird gedrückt und zeigt „Gesendet ✓“. Ein blauer Lichtpunkt läuft als dünne Linie aus dem Fenster und wird zur oberen Linie der Merkmalsliste.
- **Rechts, danach nacheinander:** die 5 Merkmale
  1. schriftliche digitale Kommunikation
  2. schnell und weltweit versendbar
  3. Anhänge möglich
  4. zeitversetzt nutzbar
  5. formell oder privat einsetzbar
- **Klein darunter:** „Geeignet für: Nachrichten, Dokumente, Schule & Beruf“

### 03 – Podcast
- **Mitte:** eine große Wellenform aus Balken mit Play-Knopf. Sie baut sich auf, dann springt Play auf Pause, und eine Abspielmarke färbt die gehörten Balken orange. Der Knopf lässt sich anklicken (Pause/Weiter).
- **Oben rechts:** „Nützlich für: Wissen, Nachrichten, Unterhaltung & Lernen“
- **Unten in 5 Spalten:** die Merkmale
  1. Audioformat
  2. jederzeit abrufbar
  3. verschiedene Themen & Zielgruppen
  4. oft als Serie oder einzelne Folgen
  5. über Plattformen und Apps verfügbar
- **Unten links, bewusst klein:** „Aber: Nicht jeder Podcast liefert sinnvolle Inhalte.“

### 04 – Ende
- **Groß:** „Danke fürs Zuhören.“
- **Klein darunter:** „E-Mail & Podcast – zwei unterschiedliche digitale Medien“
- **Visuell:** Die blaue Linie und die orange Welle aus Folie 1 laufen aufeinander zu und treffen sich in einem Punkt.
- **Unten links:** „Fragen?“

## Bedienung

| Aktion | Steuerung |
|---|---|
| Weiter | runder Knopf unten rechts („Weiter“, auf Folie 4 „Von vorn“) |
| Zurück | dezentes „← Zurück“ neben dem Knopf (auf Folie 1 ausgeblendet) |
| Tastatur | → / Leertaste / Enter / Bild ↓ = weiter, ← / Bild ↑ = zurück |

- Die Folien gleiten sanft horizontal und blenden dabei über.
- Schnelles Doppelklicken überspringt keine Folie.
- Es wird nie gescrollt.

## Gestaltung

- **Farben:** fast schwarzer Hintergrund, gebrochenes Weiß für Text, Blau (`#6aa4ff`) nur für E-Mail, Orange (`#ff7a48`) nur für Podcast. Die Farben erscheinen nur in Linien, Nummern und kleinen Details.
- **Schrift:** Inter bzw. SF Pro, sonst die Systemschrift. Titel 150–176 px, Merkmale 34–40 px (bezogen auf 1920 × 1080).
- **Layout:** Jede Folie ist anders aufgebaut (Mitte / links–rechts / Band mit Spalten / viel leerer Raum), nutzt aber dasselbe Raster mit 140 px Rand.
- **Details:** Oben rechts zeigt eine Leiste mit 4 Strichen den Fortschritt. Der aktive Strich hat die Farbe des jeweiligen Mediums.
- **Maus:** Die Grafiken verschieben sich minimal, wenn man die Maus bewegt.
- **Weiter-Knopf:** leichter Glaseffekt, angelehnt an liquid-glass-js, aber selbst nachgebaut (keine Abhängigkeit).

## Qualitätskontrolle

Getestet in Chromium bei 1920 × 1080 und 1600 × 900 mit Screenshots aller Folien.

| Prüfpunkt | Ergebnis |
|---|---|
| Genau 4 Folien | ✓ |
| Jede Folie passt auf einen Bildschirm | ✓ |
| Kein Text läuft über | ✓ (getestet mit der breiten Linux-Schrift DejaVu) |
| Schrift groß genug | ✓ |
| Klickflächen (Weiter, Zurück, Von vorn, Play) | ✓ |
| Animationen laufen und starten bei jedem Folienbesuch neu | ✓ |
| Keine externen Bilder oder Dateien | ✓ |
| JavaScript-Fehler | keine |

## Hinweise

- **Timing:** Die Merkmale erscheinen mit Absicht nicht sofort, auf der E-Mail-Folie erst nach etwa 2,7 bis 4 Sekunden, auf der Podcast-Folie nach etwa 1,8 bis 2,4 Sekunden. Wer schneller weiterklickt, sieht sie noch nicht.
- **Glaseffekt:** funktioniert nur in Chrome und Edge. Andere Browser zeigen einen einfachen Weichzeichner, die Bedienung ist überall gleich.
- **Weniger Bewegung:** Ist am Rechner „weniger Bewegung“ eingestellt, werden die Animationen übersprungen.
- **Vollbild:** Für den Vortrag den Browser mit F11 in den Vollbildmodus schalten.
