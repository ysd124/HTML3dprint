# Report – Präsentation „Digitale Medien: E-Mail & Podcast“

Erweiterte Fassung. Die ursprünglichen 4 Folien (Titel, E-Mail, Podcast, Ende) sind erhalten geblieben. Dazwischen stehen jetzt 9 neue Informationsfolien. Design, Navigation, das 16:9-Format und die Übergänge sind unverändert.

## Überblick

| | |
|---|---|
| Datei | `index.html` – eine Datei, direkt im Browser startbar, ohne Internet |
| Technik | HTML + CSS + JavaScript, SVG für Linien und Wege, keine externen Bibliotheken |
| Folien | 13 |
| Format | feste 16:9-Bühne (1920 × 1080), wird auf jeden Bildschirm skaliert |
| Extras | Sprecher-Notizen und Animationsprotokoll für jede Folie, Sprecheransicht in eigenem Fenster |

## Aufbau

| # | Folie | Kernfrage | neu? |
|---|---|---|---|
| 01 | Titel | Worum geht es? | bestehend |
| 02 | E-Mail – Einführung | Was ist eine E-Mail? | bestehend + Kernfrage |
| 03 | Technik | Wie funktioniert eine E-Mail? (Server, SMTP, IMAP/POP3) | neu |
| 04 | Versand als Ablauf | Was passiert beim Senden? (11 Schritte, 6 Schnittpunkte) | neu |
| 05 | Bestandteile | Woraus besteht eine E-Mail? (Von, An, CC, BCC, Betreff, Text, Signatur, Anhang) | neu |
| 06 | Sicherheit | Wie erkenne ich Spam & Phishing? (Warnzeichen, Passwörter, Anhänge, Datenschutz) | neu |
| 07 | Podcast – Einführung | Was ist ein Podcast? | bestehend + Kernfrage |
| 08 | Produktion | Wie entsteht eine Folge? (Mikrofon → Rohaufnahme → Schnitt → Musik → Export) | neu |
| 09 | Produktion als Ablauf | Von der Idee zum Hörer (8 Schnittpunkte) | neu |
| 10 | Verbreitung | Wie kommt der Podcast zum Hörer? (Hosting, RSS-Feed, Plattformen, Streaming/Download, Abonnieren) | neu |
| 11 | Formate & Zielgruppen | Welche Podcasts gibt es – für wen? (Formate, Zielgruppen, Einsatz, Chancen & Probleme) | neu |
| 12 | Vergleich | E-Mail und Podcast im Vergleich (inkl. Vor- und Nachteile) | neu |
| 13 | Fazit & Fragen | Was bleibt? | bestehend + Fazit an den Linien |

Die empfohlene Struktur hatte 12 Folien. Ich habe eine 13. ergänzt („Formate & Zielgruppen“), weil Formate, Zielgruppen, Einsatzbereiche sowie Chancen und Probleme sonst auf die Vergleichsfolie gepresst worden wären. Die Vor- und Nachteile beider Medien stehen auf der Vergleichsfolie.

## Bedienung

| Aktion | Steuerung |
|---|---|
| Weiter | runder Knopf unten rechts (auf der letzten Folie „Von vorn“), → / Leertaste / Enter |
| Zurück | „← Zurück“ neben dem Knopf, ← |
| Animation neu starten | Taste **R** oder „↻ Ablauf neu starten“ auf den Ablauf-Folien |
| Sprecher-Notizen einblenden | Taste **N** (Panel am unteren Rand, nochmal N blendet aus) |
| Sprecheransicht | Taste **P** öffnet ein eigenes Fenster mit Notizen, Animationsprotokoll, nächster Folie, Uhr und Steuerknöpfen. Dieses Fenster auf den Laptop ziehen, die Präsentation auf den Beamer. |

Ein kurzer Hinweis auf N / P / R erscheint auf der Titelfolie für einige Sekunden und blendet sich dann aus.

## Animationen

- **Eine Quelle für das Timing:** Alle Zeiten stehen in einem Animationsprotokoll in der `index.html` (`<script id="timeline">`). Die Einblende-Verzögerungen der Elemente werden daraus gesetzt. Notizen-Panel, Sprecheransicht und dieser Bericht zeigen dasselbe Protokoll.
- **Technik:** SVG-Pfade für alle Wege, `stroke-dasharray` / `stroke-dashoffset` zum Zeichnen der Linien, `getPointAtLength` und `requestAnimationFrame` für die wandernden Punkte, CSS-Transitions mit Ease-In/Ease-Out für Einblendungen.
- **Schnittpunkte:** kleiner Kreis, Nummer, Bezeichnung, Icon, kurze Erklärung. Ein Schnittpunkt leuchtet erst auf, wenn der Punkt ihn erreicht: Er füllt sich mit der Akzentfarbe, ein Ring breitet sich einmal aus und die Erklärung blendet ein.
- **E-Mail-Ablauf (Folie 04):** Ein kleines Briefumschlag-Symbol läuft aus dem Mailprogramm über 6 Schnittpunkte ins Postfach. Ein Zähler in der Mitte zeigt den aktuellen der 11 Schritte.
- **Podcast-Produktion (Folie 08):** Die Wellenform aus Folie 07 wird weitergeführt. Sie entsteht live bei der Aufnahme, Fehlerstellen werden markiert und herausgeschnitten, die Lücken schließen sich, die Lautstärke wird angeglichen, eine Musikspur kommt dazu, und beim Export wird alles orange und zur Datei „Folge_12.mp3“.
- **Tempo:** ruhig, mit Pausen zwischen den Stationen. Die längste Animation (Folie 04) dauert etwa 20 Sekunden.

## Design

Das bestehende Designsystem ist unverändert: dunkler Hintergrund, gebrochenes Weiß, Blau nur für E-Mail-Folien, Orange nur für Podcast-Folien, dünne Linien, große Überschriften, viel Weißraum. Alle neuen Folien haben denselben Kopf: eine kleine Kategorie in Akzentfarbe und darunter die Kernfrage als Überschrift. Die Detailinformationen stehen in den Sprecher-Notizen, nicht auf den Folien.

## Qualitätskontrolle

Getestet in Chromium bei 1920 × 1080 und 1366 × 768. Für jede Folie habe ich den Endzustand abfotografiert, für die Ablauf-Folien zusätzlich Zwischenstände.

| Prüfpunkt | Ergebnis |
|---|---|
| 13 Folien, Reihenfolge und Navigation vor/zurück | ✓ |
| Kein Text läuft aus der Folie (automatisch geprüft) | ✓ |
| Schnittpunkte leuchten nacheinander, Erklärungen erscheinen | ✓ |
| Notizen-Panel (N), Sprecheransicht (P) inkl. Fernsteuerung, Neustart (R) | ✓ |
| JavaScript-Fehler | keine |
| Externe Dateien | keine |

## Hinweise

- **Timing:** Auf den Ablauf-Folien lohnt es sich, die Animation durchlaufen zu lassen und parallel zu erzählen. Wer schneller weiterklickt, sieht die späteren Schritte noch nicht.
- **Sprecheransicht:** Sie öffnet sich als Pop-up. Blockiert der Browser das, für diese Datei Pop-ups erlauben.
- **Glaseffekt** am Weiter-Knopf: nur in Chrome und Edge, sonst einfacher Weichzeichner.
- **Vollbild:** F11.

## Animationsprotokoll und Sprecher-Notizen je Folie

Zeiten ab dem Erscheinen der Folie (Minuten:Sekunden).

### 01 – Titel

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.3 | 00:01.6 | Briefumschlag zeichnet sich (stroke-dashoffset) |
| 00:00.4 | 00:01.4 | Titel „Digitale Medien“ erscheint |
| 00:00.7 | 00:01.7 | Untertitel „E-Mail & Podcast“ erscheint |
| 00:01.0 | 00:03.6 | Linie läuft vom Umschlag nach rechts und wird zur Audio-Wellenform |
| 00:01.2 | 00:02.2 | Beschriftung „E-Mail“ erscheint |
| 00:02.6 | 00:03.6 | Beschriftung „Podcast“ erscheint |
| 00:03.6 | fortlaufend | Wellenform schwingt ruhig weiter |

**Sprecher-Notizen**

> Begrüßung. Heute geht es um zwei digitale Medien, die wir fast täglich nutzen: die **E-Mail** und den **Podcast**.
>
> Die Animation zeigt die Idee der Präsentation: Die blaue Linie startet bei einem Briefumschlag – sie steht für die E-Mail, geschriebene Nachrichten, die von A nach B laufen. Unterwegs verwandelt sie sich in eine orange Wellenform – das ist der Podcast, ein Medium zum Hören.
>
> Ablauf: Zuerst die E-Mail – was sie ist, wie sie technisch funktioniert, woraus sie besteht und worauf man bei der Sicherheit achten muss. Danach der Podcast – wie eine Folge entsteht und wie sie zum Hörer kommt. Zum Schluss vergleichen wir beide Medien.

### 02 – E-Mail – Einführung

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.1 | 00:01.1 | Mail-Fenster erscheint, Kernfrage und Überschrift „E-Mail“ |
| 00:00.6 | 00:01.9 | Textzeilen im Fenster bauen sich auf |
| 00:01.6 | 00:02.0 | „Senden“ wird gedrückt → „Gesendet ✓“ |
| 00:01.8 | 00:03.2 | Lichtpunkt läuft als dünne Linie zur Merkmalsliste |
| 00:02.7 | 00:04.5 | Merkmale 01–05 erscheinen nacheinander |
| 00:04.0 | 00:05.0 | „Geeignet für …“ erscheint |

**Sprecher-Notizen**

> Eine **E-Mail** (electronic mail, „elektronische Post“) ist eine schriftliche Nachricht, die über das Internet von einem Postfach in ein anderes geschickt wird. Jeder Teilnehmer braucht dafür eine eigene Adresse, z. B. name@anbieter.de.
>
> Die Animation zeigt das Grundprinzip: Die Nachricht wird geschrieben, abgeschickt und läuft als Linie zu den Merkmalen.
>
> **Merkmale:** schriftlich und digital; in Sekunden weltweit zugestellt; Dokumente, Bilder oder Präsentationen können angehängt werden; **zeitversetzt** – der Empfänger muss nicht gleichzeitig online sein, die Nachricht wartet im Postfach; formell (Bewerbung, Schule) oder privat (Familie, Freunde) nutzbar.
>
> **Einsatzbereiche:** In der Schule für Hausaufgaben und den Kontakt zu Lehrkräften, im Beruf für Absprachen, Bewerbungen und Dokumente, privat für Anmeldungen, Bestellungen und Kontakt.

### 03 – Wie funktioniert eine E-Mail?

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Kernfrage und Überschrift erscheinen |
| 00:01.0 | 00:02.6 | Fünf Stationen erscheinen nacheinander (Absender → Empfänger) |
| 00:01.4 | 00:03.8 | Verbindungen zwischen den Stationen werden gezeichnet |
| 00:03.0 | 00:03.9 | Protokolle SMTP und IMAP / POP3 werden beschriftet |
| 00:03.9 | 00:05.4 | Erklärungen SMTP, IMAP und POP3 erscheinen |
| 00:05.6 | fortlaufend | Ein Punkt läuft alle 7 s ruhig vom Absender zum Empfänger |

**Sprecher-Notizen**

> Wenn man eine E-Mail verschickt, geht sie nicht direkt zum Computer des Empfängers. Sie läuft über mehrere Stationen – ähnlich wie ein Brief über Postämter.
>
> **1. Absender:** Man schreibt im Mailprogramm (z. B. Outlook, Thunderbird, Mail-App) oder im Browser (Webmail). **2. Mailserver:** Das Programm übergibt die Nachricht an den Postausgangsserver des eigenen Anbieters. Dafür nutzt es **SMTP** – Simple Mail Transfer Protocol.
>
> **3. Internet:** Der Server schaut auf den Teil hinter dem @, die **Domain** (z. B. schule.de). Über das Domain-Namen-System (DNS) findet er heraus, welcher Mailserver für diese Domain zuständig ist, und schickt die Mail ebenfalls per SMTP dorthin. **4. Empfänger-Server:** Er nimmt die Mail an und legt sie im Postfach ab. **5. Empfänger:** Er holt die Mail ab.
>
> Beim Abrufen gibt es zwei Verfahren: Mit **IMAP** bleiben die Mails auf dem Server – Handy, Laptop und Tablet zeigen dasselbe Postfach. Mit **POP3** werden die Mails auf ein Gerät heruntergeladen und meist vom Server gelöscht. Heute ist IMAP Standard.
>
> Merksatz: **SMTP zum Senden, IMAP oder POP3 zum Abrufen.**

### 04 – Der Weg einer E-Mail

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Kernfrage und Überschrift erscheinen |
| 00:00.8 | 00:01.8 | Mailprogramm (Absender), Schritt-Zähler und Postfach (Empfänger) erscheinen |
| 00:01.4 | 00:03.2 | Verbindungslinie wird gezeichnet |
| 00:02.0 | 00:03.2 | Schnittpunkte 01–06 erscheinen nacheinander |
| 00:03.4 | 00:04.8 | Schritt 1: Nachricht wird geschrieben – 01 Verfassen leuchtet |
| 00:05.0 | 00:06.0 | Schritt 2: Empfängeradresse wird eingetippt |
| 00:06.4 | 00:07.1 | Schritt 3: Betreff wird eingetragen |
| 00:07.6 | 00:08.2 | Schritt 4: Datei wird angehängt |
| 00:08.6 | 00:09.2 | Schritt 5: „Senden“ wird gedrückt |
| 00:09.4 | 00:10.4 | Schritt 6: E-Mail verlässt den Computer – 02 Senden leuchtet |
| 00:10.8 | 00:12.0 | Schritt 7: Übertragung zum Mailserver – 03 leuchtet |
| 00:12.6 | 00:13.8 | Schritt 8: Mailserver leitet weiter – 04 leuchtet |
| 00:14.4 | 00:15.6 | Schritt 9: Ankunft beim Empfänger-Server – 05 leuchtet |
| 00:16.2 | 00:17.4 | Schritt 10: neue Nachricht im Postfach – 06 Empfang leuchtet |
| 00:18.6 | 00:19.6 | Schritt 11: Nachricht wird geöffnet |

**Sprecher-Notizen**

> Diese Folie zeigt den kompletten Weg einer E-Mail in elf Schritten. Am besten erzählt man parallel zur Animation – der Zähler in der Mitte zeigt immer, welcher Schritt gerade läuft.
>
> **Schritte 1–4 (Verfassen):** Zuerst wird die Nachricht geschrieben, dann die Empfängeradresse eingetragen, ein aussagekräftiger Betreff ergänzt und eine Datei angehängt. Bis hierhin liegt alles nur auf dem eigenen Gerät.
>
> **Schritt 5–6 (Senden):** Mit dem Klick auf „Senden“ verlässt die Mail den Computer. Das Mailprogramm baut eine Verbindung zum Mailserver auf – heute fast immer verschlüsselt (TLS).
>
> **Schritt 7–8 (Mailserver, Weiterleitung):** Der eigene Mailserver nimmt die Mail per SMTP an, prüft sie und sucht über die Domain den zuständigen Server des Empfängers. Dann leitet er sie über das Internet weiter.
>
> **Schritt 9–11 (Empfang):** Der Empfänger-Server speichert die Mail im Postfach. Beim Empfänger erscheint eine neue Nachricht – er ruft sie per IMAP oder POP3 ab und öffnet sie.
>
> Wichtig: In Wirklichkeit dauert das nur Sekunden. Ist die Adresse falsch, kommt eine automatische Fehlermeldung zurück („unzustellbar“). Mit der Taste **R** oder dem Knopf „Ablauf neu starten“ lässt sich die Animation wiederholen.

### 05 – Bestandteile einer E-Mail

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Kernfrage und Überschrift erscheinen |
| 00:00.5 | 00:01.5 | Mail-Fenster erscheint |
| 00:01.6 | 00:02.3 | Von: Feld leuchtet, Linie und Erklärung erscheinen |
| 00:02.3 | 00:03.0 | An: Feld leuchtet, Erklärung erscheint |
| 00:03.0 | 00:03.7 | CC: Feld leuchtet, Erklärung erscheint |
| 00:03.7 | 00:04.4 | BCC: Feld leuchtet, Erklärung erscheint |
| 00:04.4 | 00:05.1 | Betreff: Feld leuchtet, Erklärung erscheint |
| 00:05.1 | 00:05.8 | Text: Feld leuchtet, Erklärung erscheint |
| 00:05.8 | 00:06.5 | Signatur: Feld leuchtet, Erklärung erscheint |
| 00:06.5 | 00:07.2 | Anhang: Feld leuchtet, Erklärung erscheint |

**Sprecher-Notizen**

> Jede E-Mail besteht aus einem **Kopf** (Von, An, CC, BCC, Betreff) und einem **Inhalt** (Text, Signatur, Anhänge).
>
> **Adresse:** Sie besteht aus Benutzername, dem @ („at“) und der Domain des Anbieters – z. B. max.muster@mail.de. Die Domain bestimmt, welcher Server die Mail bekommt. **Von / An:** Absender und Empfänger – bei „An“ können auch mehrere Adressen stehen.
>
> **CC** (Carbon Copy) heißt Kopie: Alle sehen, wer die Mail außerdem bekommt. **BCC** (Blind Carbon Copy) ist eine Blindkopie: Diese Empfänger bleiben für alle anderen unsichtbar. Beispiel: Eine Rundmail an viele Eltern gehört in BCC, damit nicht jeder alle Adressen sieht – das ist auch Datenschutz.
>
> **Betreff:** kurz und eindeutig, damit der Empfänger sofort weiß, worum es geht. **Text:** Anrede, Inhalt, Gruß. In Schule und Beruf formell („Sehr geehrte Frau Weber“), privat locker („Hallo“). **Signatur:** Name und Kontaktdaten, die automatisch unter jede Mail gesetzt werden.
>
> **Anhänge:** Dateien wie PDF, Bilder oder Präsentationen. Viele Anbieter begrenzen die Größe auf etwa 20–25 MB – große Dateien verschickt man besser als Cloud-Link.

### 06 – Sicherheit: Spam und Phishing

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Kernfrage und Überschrift erscheinen |
| 00:00.6 | 00:01.6 | Beispiel einer Phishing-Mail erscheint |
| 00:01.0 | 00:02.3 | Begriffe Spam und Phishing werden erklärt |
| 00:02.4 | 00:03.2 | Warnzeichen 1: Absenderadresse wird markiert |
| 00:03.3 | 00:04.1 | Warnzeichen 2: Zeitdruck im Betreff |
| 00:04.2 | 00:05.0 | Warnzeichen 3: unpersönliche Anrede |
| 00:05.1 | 00:05.9 | Warnzeichen 4: gefälschter Link |
| 00:06.0 | 00:06.8 | Warnzeichen 5: gefährlicher Anhang |
| 00:07.1 | 00:08.4 | Vier Schutzregeln erscheinen nacheinander |

**Sprecher-Notizen**

> **Spam** sind unerwünschte Massen-Mails, meistens Werbung. Mailanbieter filtern sie automatisch in den Spam-Ordner. **Phishing** ist gefährlicher: Betrüger fälschen Mails von Banken, Paketdiensten oder Shops, um an Passwörter, Kontodaten oder persönliche Informationen zu kommen („Passwort-Fishing“).
>
> Die Beispiel-Mail zeigt fünf typische Warnzeichen: **1** eine seltsame Absenderadresse mit fremder Domain, **2** Zeitdruck und Drohung im Betreff, **3** eine unpersönliche Anrede („Sehr geehrter Kunde“), **4** ein Button, dessen Link auf eine fremde Seite führt – mit der Maus darüberfahren zeigt die echte Adresse – und **5** ein Anhang mit doppelter Endung: „.pdf.exe“ ist in Wahrheit ein Programm.
>
> **Schutz:** Passwörter sollten lang sein (mindestens 12 Zeichen, gerne ein Satz), für jeden Dienst anders und in einem Passwort-Manager liegen. Zusätzlich die Zwei-Faktor-Anmeldung einschalten. Anhänge nur öffnen, wenn man den Absender kennt und die Datei erwartet – besonders vorsichtig bei .exe, .zip oder Office-Dateien mit Makros.
>
> **Datenschutz:** Eine normale E-Mail ist wie eine Postkarte – auf dem Weg ist sie nicht immer geschützt. Passwörter, Gesundheits- oder Kontodaten gehören nicht unverschlüsselt in eine Mail; dafür gibt es Ende-zu-Ende-Verschlüsselung (S/MIME, PGP). Seriöse Banken fragen nie per Mail nach Passwörtern. Bei Verdacht: nicht antworten, nichts anklicken, löschen oder melden.

### 07 – Podcast – Einführung

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.2 | 00:01.2 | Kernfrage und Überschrift „Podcast“ |
| 00:00.3 | 00:01.6 | Wellenform baut sich auf |
| 00:00.6 | 00:01.6 | „Nützlich für …“ erscheint |
| 00:01.5 | fortlaufend | Play wechselt zu Pause, Abspielmarke läuft, gespielte Balken werden orange |
| 00:01.8 | 00:03.4 | Merkmale 01–05 erscheinen nacheinander |
| 00:03.2 | 00:04.2 | „Aber: …“ erscheint |

**Sprecher-Notizen**

> Ein **Podcast** ist eine Serie von Audiodateien – sogenannten Folgen oder Episoden –, die man im Internet jederzeit abrufen kann. Der Name setzt sich aus „iPod“ und „Broadcast“ (Rundfunk) zusammen.
>
> Anders als beim Radio entscheidet der Hörer selbst, wann und wo er hört („on demand“). Podcasts erscheinen meist regelmäßig zu einem festen Thema und können abonniert werden – neue Folgen kommen dann automatisch.
>
> Die Wellenform zeigt das Wesentliche: Ein Podcast ist Ton. Die Abspielmarke läuft, die gehörten Teile werden orange.
>
> Kritisch: Jeder kann einen Podcast veröffentlichen, es gibt keine Redaktion, die prüft. Darum sollte man sich fragen: Wer spricht? Welche Quellen gibt es? Ist es Werbung?

### 08 – Wie entsteht ein Podcast?

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Kernfrage und Überschrift erscheinen |
| 00:00.8 | 00:02.4 | Stationen-Leiste wird gezeichnet, Schnittpunkte 01–05 erscheinen |
| 00:01.6 | 00:02.4 | Mikrofon und Spur „Stimme“ erscheinen |
| 00:02.4 | 00:06.4 | 01 Mikrofon: Aufnahme läuft (REC) – Wellenform entsteht von links nach rechts |
| 00:06.8 | 00:08.6 | 02 Rohaufnahme: Versprecher, Pause und Störgeräusch werden markiert |
| 00:09.4 | 00:10.8 | 03 Schnitt: markierte Stellen werden entfernt, die Lücken schließen sich |
| 00:11.0 | 00:12.0 | 03 Schnitt: Lautstärke wird angeglichen, Rauschen entfernt |
| 00:12.8 | 00:14.4 | 04 Musik & Effekte: Musikspur mit Intro und Outro baut sich auf |
| 00:15.4 | 00:17.0 | 05 Export: Spuren werden zusammengemischt, Exportbalken läuft |
| 00:17.0 | 00:18.0 | Fertige Audiodatei „Folge_12.mp3“ – bereit für den Upload |

**Sprecher-Notizen**

> Hier sieht man, wie aus einer Aufnahme eine fertige Folge wird. Die Wellenform verändert sich bei jeder Station.
>
> **01 Mikrofon / Aufnahme:** Ein USB-Mikrofon reicht für den Anfang, zur Not auch das Smartphone. Wichtig sind 10–20 cm Abstand zum Mund, ein Poppschutz gegen harte „P“- und „B“-Laute und ein ruhiger Raum – Teppiche, Vorhänge oder ein Kleiderschrank schlucken Hall.
>
> **02 Rohaufnahme:** Die Aufnahme ist nie perfekt: Versprecher, lange Pausen, Husten, ein vorbeifahrendes Auto. Diese Stellen werden markiert.
>
> **03 Audioschnitt:** Mit Programmen wie Audacity (kostenlos) oder GarageBand werden die markierten Stellen herausgeschnitten – die Lücken schließen sich. Danach wird die Lautstärke angeglichen (Normalisieren) und Rauschen reduziert.
>
> **04 Musik & Effekte:** Ein kurzes Intro und Outro machen die Folge wiedererkennbar, leise Hintergrundmusik und Soundeffekte trennen Abschnitte. Achtung Urheberrecht: nur lizenzfreie oder selbst gemachte Musik verwenden.
>
> **05 Export:** Am Ende werden alle Spuren zu einer Datei zusammengemischt, meist als MP3 – gute Qualität bei kleiner Dateigröße. Dazu kommen Titel, Folgennummer und ein Cover-Bild.

### 09 – Podcast-Produktion als Ablauf

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Kernfrage und Überschrift erscheinen |
| 00:01.0 | 00:02.8 | Wellenförmige Verbindungslinie wird gezeichnet |
| 00:01.4 | 00:02.8 | Schnittpunkte 01–08 erscheinen nacheinander |
| 00:02.8 | 00:03.6 | Punkt startet: 01 Idee leuchtet, Erklärung erscheint |
| 00:03.4 | 00:04.6 | Punkt wandert zu 02 Recherche – leuchtet, Erklärung erscheint |
| 00:05.2 | 00:06.4 | Punkt wandert zu 03 Aufnahme |
| 00:07.0 | 00:08.2 | Punkt wandert zu 04 Schnitt |
| 00:08.8 | 00:10.0 | Punkt wandert zu 05 Export |
| 00:10.6 | 00:11.8 | Punkt wandert zu 06 Veröffentlichung |
| 00:12.4 | 00:13.6 | Punkt wandert zu 07 Plattform |
| 00:14.2 | 00:15.4 | Punkt erreicht 08 Hörer – Ablauf komplett |

**Sprecher-Notizen**

> Diese Folie zeigt den gesamten Weg einer Podcast-Folge in acht Stationen. Der Punkt wandert entlang der Linie; an jeder Station leuchtet der Punkt auf und die Erklärung erscheint.
>
> **01 Idee:** Thema, Zielgruppe, Format und Länge festlegen – worüber spreche ich, für wen? **02 Recherche:** Fakten sammeln, Quellen prüfen, ein Skript oder Stichpunkte schreiben, eventuell Gäste einladen.
>
> **03 Aufnahme** und **04 Schnitt** haben wir gerade gesehen. **05 Export:** Alles wird zu einer MP3-Datei zusammengefügt.
>
> **06 Veröffentlichung:** Die Datei wird bei einem Hosting-Dienst hochgeladen, zusammen mit Titel, Beschreibung (Shownotes) und Cover. **07 Plattform:** Podcast-Apps und Streaming-Dienste übernehmen die neue Folge automatisch. **08 Hörer:** Hören, abonnieren, bewerten, Feedback geben.
>
> Wichtig: Der größte Teil der Arbeit passiert vor und nach der Aufnahme – Planung und Schnitt dauern oft länger als das Sprechen selbst.

### 10 – Wie kommt der Podcast zum Hörer?

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Kernfrage und Überschrift erscheinen |
| 00:01.0 | 00:02.6 | Stationen erscheinen, Verbindungen werden gezeichnet |
| 00:02.8 | 00:03.4 | Upload: „Folge_12.mp3“ wandert ins Hosting – Hosting leuchtet |
| 00:03.8 | 00:05.0 | Datenpunkt läuft zum RSS-Feed – neuer Eintrag „Folge 12“ leuchtet |
| 00:05.6 | 00:07.0 | Feed verteilt die Folge gleichzeitig an drei Plattformen |
| 00:07.6 | 00:08.8 | Plattformen liefern an den Hörer – Hörer leuchtet |
| 00:09.2 | 00:10.0 | „Streaming / Download“ wird eingeblendet |
| 00:10.2 | 00:11.8 | Abonnieren: Punkt läuft vom Hörer zurück zum Feed |
| 00:12.0 | 00:12.8 | „Neue Folgen kommen automatisch“ wird eingeblendet |
| 00:13.0 | fortlaufend | Verteilung wiederholt sich ruhig alle 8 s |

**Sprecher-Notizen**

> Nach dem Export muss die Folge zu den Hörern kommen. Dafür gibt es eine geschickte Technik: einmal hochladen – überall verfügbar.
>
> **Hosting:** Die MP3-Datei wird bei einem Podcast-Hoster hochgeladen. Das ist ein Speicherdienst im Internet, der die Dateien bereitstellt und automatisch den RSS-Feed erstellt.
>
> **RSS-Feed:** RSS steht für „Really Simple Syndication“. Der Feed ist eine Textdatei (XML) mit einer Liste aller Folgen – Titel, Beschreibung und Link zur Audiodatei. Kommt eine neue Folge dazu, bekommt der Feed einen neuen Eintrag.
>
> **Plattformen:** Podcast-Apps, Streaming-Dienste und Websites lesen den Feed regelmäßig. Sobald dort eine neue Folge steht, erscheint sie überall gleichzeitig – der Podcaster muss sie nicht einzeln hochladen.
>
> **Hörer:** Beim **Streaming** wird die Folge direkt abgespielt, man braucht Internet. Beim **Download** landet die Datei auf dem Gerät und man kann offline hören, z. B. im Zug. Wer **abonniert**, bekommt jede neue Folge automatisch angezeigt oder heruntergeladen – die App prüft dafür den Feed. Die meisten Podcasts sind kostenlos und finanzieren sich über Werbung oder Spenden.

### 11 – Formate und Zielgruppen

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Kernfrage und Überschrift erscheinen |
| 00:00.8 | 00:03.2 | Fünf Formate erscheinen, ihre Sprecher-Wellenformen bauen sich auf |
| 00:03.0 | 00:04.0 | Zielgruppen erscheinen |
| 00:03.8 | 00:04.8 | Einsatzbereiche erscheinen |
| 00:05.0 | 00:06.3 | Chancen und Probleme erscheinen |

**Sprecher-Notizen**

> Podcasts gibt es in vielen Formaten. Die kleinen Wellenformen zeigen, wer wie viel spricht. **Interview:** Moderator und Gast wechseln sich ab. **Solo:** Eine Person erklärt ein Thema – z. B. Lern-Podcasts. **Gesprächsrunde:** mehrere Stimmen, schnelle Wechsel, oft locker. **Storytelling:** Eine Geschichte wird erzählt, mit Musik und Geräuschen – ähnlich wie ein Hörspiel, z. B. True-Crime oder Geschichts-Podcasts. **Nachrichten:** kurze, tägliche Folgen mit dem Wichtigsten.
>
> **Zielgruppen:** Schüler und Studierende zum Lernen, Pendler auf dem Weg zur Arbeit, Menschen mit einem bestimmten Hobby, Kinder mit Hörgeschichten. **Einsatz:** Bildung, Nachrichten, Unterhaltung – und Unternehmen nutzen Podcasts für Marketing oder interne Kommunikation.
>
> **Chancen:** Die Hürde ist niedrig – jeder mit Mikrofon kann einen Podcast starten. Man kann nebenbei hören (Sport, Bus, Hausarbeit), und auch sehr spezielle Themen finden ihr Publikum. Die Stimme schafft Nähe.
>
> **Probleme:** Es gibt keine Redaktion, die Inhalte prüft – Meinungen werden manchmal wie Fakten präsentiert, Falschinformationen verbreiten sich. Lange Folgen sind schwer durchsuchbar, und Werbung ist nicht immer klar erkennbar. Deshalb gilt: Wer spricht? Welche Quellen werden genannt?

### 12 – E-Mail und Podcast im Vergleich

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.0 | 00:01.0 | Überschrift erscheint |
| 00:00.8 | 00:02.6 | Spalten E-Mail / Podcast mit blauer Linie und oranger Welle |
| 00:01.6 | 00:04.7 | Sieben Vergleichszeilen erscheinen nacheinander |

**Sprecher-Notizen**

> Zum Schluss legen wir beide Medien nebeneinander. **Form:** Die E-Mail ist geschriebener Text mit Anhängen, der Podcast ist gesprochenes Audio in Folgen.
>
> **Richtung:** Die E-Mail ist ein Austausch – man kann direkt antworten. Beim Podcast spricht einer und viele hören zu; Rückmeldung gibt es höchstens über Kommentare oder Bewertungen.
>
> **Zeit:** Beide sind zeitversetzt nutzbar. Die E-Mail kommt in Sekunden an und wartet im Postfach, der Podcast kann jederzeit abgerufen werden. **Technik:** E-Mail läuft über Mailserver mit SMTP und IMAP/POP3, der Podcast über Hosting und RSS-Feed.
>
> **Vorteile:** E-Mail ist schnell, kostenlos und eignet sich für Dokumente; Podcasts sind flexibel und nebenbei hörbar. **Nachteile:** Bei E-Mails Spam, Phishing und zu viele Nachrichten; bei Podcasts ungeprüfte Inhalte und keine direkte Rückfrage.
>
> Gemeinsam ist beiden: Man braucht **Medienkompetenz** – bei der E-Mail, um Betrug zu erkennen, beim Podcast, um gute von schlechten Inhalten zu unterscheiden.

### 13 – Fazit & Fragen

**Animationsprotokoll**

| Start | Ende | Ablauf |
|---|---|---|
| 00:00.2 | 00:01.2 | „Danke fürs Zuhören.“ erscheint |
| 00:00.6 | 00:01.6 | Untertitel erscheint |
| 00:00.9 | 00:02.9 | E-Mail-Linie und Audio-Wellenform laufen aufeinander zu |
| 00:02.0 | 00:03.0 | Fazit-Beschriftungen an beiden Linien |
| 00:02.8 | 00:04.7 | Treffpunkt leuchtet auf, Ring breitet sich aus |
| 00:03.0 | 00:04.0 | „Fragen?“ erscheint |

**Sprecher-Notizen**

> **Fazit:** E-Mail und Podcast sind zwei unterschiedliche digitale Medien. Die E-Mail dient dem schriftlichen **Austausch** – schnell, gezielt, mit Anhängen, technisch über Mailserver mit SMTP und IMAP/POP3. Der Podcast dient dem **Zuhören und Lernen** – flexibel, jederzeit abrufbar, verbreitet über Hosting und RSS-Feed.
>
> Die beiden Linien treffen sich: Beide Medien sind zeitversetzt nutzbar, und bei beiden braucht man Medienkompetenz – Phishing erkennen und Inhalte kritisch prüfen.
>
> Danke fürs Zuhören – jetzt ist Zeit für Fragen. Mögliche Fragen: Was ist der Unterschied zwischen CC und BCC? Warum braucht ein Podcast einen RSS-Feed? Woran erkennt man Phishing?
