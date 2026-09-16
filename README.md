<p align="center">
  <img src="https://raw.githubusercontent.com/Seb88123/brabbel-releases/main/assets/brabbel.svg" width="96" alt="Brabbel">
</p>

<h1 align="center">Brabbel</h1>

<p align="center"><strong>Brabbel drauflos. Der Text kommt trotzdem ordentlich raus.</strong></p>

<p align="center">
  Diktieren in jede Windows-Anwendung. Spracherkennung und Textüberarbeitung laufen komplett auf deinem PC.<br>
  Kein Abo, kein Konto, keine Cloud.
</p>

<p align="center">
  <a href="https://github.com/Seb88123/brabbel-releases/releases/latest"><img alt="Neueste Version" src="https://img.shields.io/github/v/release/Seb88123/brabbel-releases?label=Download&color=2f9e5b"></a>
  <a href="https://github.com/Seb88123/brabbel-releases/releases"><img alt="Downloads" src="https://img.shields.io/github/downloads/Seb88123/brabbel-releases/total?color=2f9e5b"></a>
  <img alt="Plattform" src="https://img.shields.io/badge/Windows-10%20%7C%2011%20(64%20Bit)-0078d4">
  <img alt="Lizenz" src="https://img.shields.io/badge/Lizenz-GPL--3.0-blue">
</p>

<p align="center">
  <a href="https://github.com/Seb88123/brabbel-releases/releases/latest"><strong>⬇ BrabbelSetup.exe herunterladen</strong></a>
</p>

---

## Was Brabbel macht

Du hältst einen Hotkey gedrückt, sprichst, lässt los. Einen Moment später steht der Text dort, wo gerade dein Cursor blinkt: in der E-Mail, im Chat, im Dokument, im Ticket, im Code-Editor. Brabbel tippt ihn für dich ein, als hättest du ihn selbst geschrieben.

Das Besondere: **Nichts verlässt deinen Rechner.** Die Spracherkennung läuft mit Whisper-Modellen lokal auf CPU oder Grafikkarte. Die optionale Textüberarbeitung nutzt ein lokales Sprachmodell. Es gibt keinen Server, der mithört, keine Nutzungsgebühr und keine Datenschutzerklärung, die du lesen müsstest, bevor du ein vertrauliches Diktat sprichst.

Brabbel ist auf Deutsch gebaut, für deutsche Diktate und mit einer komplett deutschen Oberfläche.

## Warum Brabbel?

- **Wirklich lokal.** Audio, Transkript und Textüberarbeitung bleiben auf deinem Gerät. Internet brauchst du nur einmal, um Modelle herunterzuladen.
- **Funktioniert überall.** Brabbel schreibt in jedes normale Textfeld: Outlook, Teams, Word, Browser, VS Code, Terminal. Kein Plugin, keine Integration nötig.
- **Zwei Arten zu diktieren.** Push-to-Talk zum Halten oder Umschalten per Tastendruck. Beide gleichzeitig aktiv, jeweils mit eigenem Hotkey.
- **Aus Gebrabbel wird Text.** Die optionale Textüberarbeitung entfernt Füllwörter, korrigiert Grammatik, macht aus dem Diktat eine formelle E-Mail oder übersetzt ins Englische. Sieben Stile, alle Prompts editierbar.
- **Antworten statt abtippen.** Im Desktop-Widget markierst du eine erhaltene E-Mail, sagst „Termin bestätigen, Unterlagen folgen Montag“ und bekommst die fertige Antwort im passenden Ton.
- **Deine Wörter, richtig geschrieben.** Namen, Produkte und Fachbegriffe kommen ins Wörterbuch. Ersetzungsregeln korrigieren typische Hörfehler automatisch.
- **Schnell auf jeder Hardware.** NVIDIA per CUDA, AMD und Intel per Vulkan, sonst CPU. Mit Live-Erkennung beginnt die Verarbeitung schon während du sprichst.
- **Nichts geht verloren.** Jedes Diktat landet in der lokalen Historie. Die Schnell-Historie holt das letzte Diktat per Hotkey zurück, falls es im falschen Fenster gelandet ist.
- **Sieht gut aus.** Sechs animierte Overlay-Designs zeigen, dass Brabbel zuhört. Auf Wunsch leuchtet die RGB-Beleuchtung von Tastatur, Maus oder Gehäuse mit.
- **Ehrliche Zahlen.** Der Insights-Bereich zeigt Wartezeit, Sprechtempo, gesparte Tippzeit und welches Modell auf deiner Hardware wie schnell ist.
- **Ohne Adminrechte.** Installation in dein Benutzerprofil, signierte Updates aus der App heraus, saubere Deinstallation über Apps & Features.

## Installation in drei Minuten

1. **[BrabbelSetup.exe](https://github.com/Seb88123/brabbel-releases/releases/latest)** herunterladen und starten. Windows SmartScreen kann beim ersten Start warnen, weil der Installer nicht mit einem Zertifikat signiert ist. Über **Weitere Informationen → Trotzdem ausführen** geht es weiter.
2. Der Assistent prüft Windows-Version, Arbeitsspeicher, freien Speicher, Grafikkarte und Mikrofonzugriff.
3. Du wählst ein Whisper-Modell und, falls gewünscht, GPU-Beschleunigung, Textüberarbeitung und RGB-Beleuchtung. Bei erkannter Grafikkarte sind CUDA beziehungsweise Vulkan und das Modell `large-v3-turbo` vorausgewählt, sonst `small`.
4. Das Setup lädt nur die Komponenten, die du ausgewählt hast, prüft jeden Download per SHA-256 und startet Brabbel.

Brabbel läuft danach als grüne Kachel im Infobereich der Taskleiste. Beim Start zeigt eine kleine Karte, ob Mikrofon, Modell und Hotkey bereit sind.

## Erste Schritte

| Aktion | Standard |
| --- | --- |
| Push-to-Talk: halten, sprechen, loslassen | **Strg + Win** |
| Umschalten: einmal drücken startet, erneut drücken stoppt | nicht belegt, frei einlernbar |
| Schnell-Historie: letzte Diktate als Karte über dem Tray | **Strg + Win + H** |
| Einstellungen öffnen | Doppelklick auf das Tray-Symbol |

1. In ein Textfeld klicken.
2. **Strg + Win** gedrückt halten und sprechen. Das Overlay am unteren Bildschirmrand zeigt den Pegel.
3. Loslassen. Brabbel verarbeitet lokal und tippt den Text ein.

Alle Hotkeys lassen sich unter **Aufnahme → Hotkey & Modus** einlernen, auch Kombinationen nur aus Zusatztasten wie `Strg + Shift`. Eine per Umschalten gestartete Aufnahme endet nach einstellbarer Stille von selbst.

## Funktionen im Detail

### Spracherkennung

Brabbel nutzt Whisper-Modelle von OpenAI über [faster-whisper](https://github.com/SYSTRAN/faster-whisper) oder [whisper.cpp](https://github.com/ggml-org/whisper.cpp). Du wählst, wie viel Genauigkeit du gegen Geschwindigkeit tauschst:

| Modell | Download | Wofür |
| --- | --- | --- |
| `tiny` | ca. 75 MB | Schwache Rechner, kurze Kommandos |
| `base` | ca. 140 MB | Schneller Alltag auf älteren Laptops |
| `small` | ca. 470 MB | Guter Kompromiss auf CPU, Standard ohne GPU |
| `medium` | ca. 1,5 GB | Höhere Genauigkeit, braucht GPU oder Geduld |
| `large-v3-turbo` | ca. 1,6 GB | Beste Wahl mit Grafikkarte, Standard mit GPU |
| `large-v3` | ca. 3 GB | Maximale Genauigkeit |

Modelle werden nur auf deinen ausdrücklichen Klick heruntergeladen und liegen unter `%LOCALAPPDATA%\Brabbel`. Beim Diktieren findet nie ein Download statt.

**Live-Erkennung** (optional): Brabbel erkennt Sprechpausen mit einem winzigen VAD-Modell und transkribiert abgeschlossene Abschnitte bereits während der Aufnahme. Nach dem Loslassen bleibt nur noch der letzte Satz, die Wartezeit hängt kaum noch von der Diktatlänge ab. Auf Wunsch erscheint der erkannte Text live in einer Glasleiste über dem Overlay.

**Keine erfundenen Wörter**: Enthält eine Aufnahme keine Sprache, geht sie gar nicht erst an Whisper. Statt „Piano“ oder „Grazie“ aus Mikrofonrauschen meldet Brabbel „Keine Sprache erkannt“.

### Textüberarbeitung mit lokalem Sprachmodell

Optional installiert Brabbel Qwen3-4B über [llama.cpp](https://github.com/ggml-org/llama.cpp), rund 2,5 GB. Danach kannst du jedes Diktat automatisch in einen Stil bringen:

| Stil | Ergebnis |
| --- | --- |
| **Geglättet** | Füllwörter und Wiederholungen raus, Grammatik und Zeichensetzung korrigiert, Wortwahl bleibt |
| **Formell** | Sachlicher Geschäftston in der Sie-Form |
| **Kurz & knapp** | Auf das Wesentliche gekürzt |
| **E-Mail** | Anrede, Absätze, Grußformel |
| **Locker** | Chat-Ton ohne Floskeln |
| **Englisch** | Natürliche Übersetzung |
| **Individuell** | Dein eigener Prompt |

Jeder Prompt ist editierbar und zurücksetzbar. Ein eingebauter Schutztext sorgt dafür, dass das Modell Anweisungen im Diktat nicht ausführt, sondern nur den Text überarbeitet. Original und überarbeitete Fassung bleiben in der Historie beide abrufbar. Das Sprachmodell läuft ausschließlich auf `127.0.0.1`, nichts geht ins Internet.

### Desktop-Widget mit Kontextmodus (Alpha)

Statt direkt ins Textfeld zu tippen, kann Brabbel als kleine, frei verschiebbare Glasleiste im Vordergrund bleiben. Nach dem Diktat klappt der Text als bearbeitbares Fenster auf: **Original** ansehen, **Stil ändern**, **Kopieren**, **Verwerfen**.

Der **Kontextmodus** macht daraus einen Antwort-Assistenten: Markiere eine erhaltene E-Mail, starte die Aufnahme und sag, was du antworten willst. Brabbel liest die Markierung, erkennt Anrede und Absender, und das Textmodell schreibt die fertige Antwort im gewählten Stil. Der Kontext geht nur an das lokale Modell und wird nirgends gespeichert.

Der Modus ist als Alpha gekennzeichnet: Er funktioniert, aber Verhalten und Prompts können sich noch ändern.

### Wörterbuch und Ersetzungen

- **Begriffe**: Namen, Orte, Produkte und Abkürzungen, die Whisper als Kontext mitbekommt und dadurch deutlich wahrscheinlicher richtig schreibt. Import aus Textdatei möglich.
- **Ersetzungen**: Regeln „Whisper schreibt → Brabbel fügt ein“, ganzes Wort oder Teilwort, mit oder ohne Groß-/Kleinschreibung. Greifen bei jedem Diktat, vor Stil und Einfügen.

Beides funktioniert ohne Textüberarbeitung und mit allen Engines.

### Historie und Schnell-Historie

Alle Diktate werden lokal mit Datum und Uhrzeit in einer SQLite-Datei gespeichert, durchsuchbar, kopierbar, einzeln oder gesammelt löschbar. Audio wird nie archiviert. Die Speicherung lässt sich abschalten.

Die **Schnell-Historie** (Strg + Win + H) zeigt die letzten Diktate als Karte über dem Tray. **Enter** tippt das gewählte Diktat in das Fenster, das vorher aktiv war. So ist ein Diktat im falschen Fenster in zwei Sekunden repariert.

### Overlay und RGB

Sechs Overlay-Designs mit Live-Vorschau: **Kapsel**, **Lichtsaum**, **Orb**, **Matrix**, **Konstellation** und **Dot-Matrix**. Alle reagieren auf deine Stimme, passen sich hellem und dunklem Hintergrund an und nehmen weder Fokus noch Mausklicks weg.

Mit **OpenRGB** und dem Logitech G HUB SDK kann Brabbel Tastatur, Maus, Mainboard oder Lüfter in einer Farbe leuchten lassen, solange es zuhört. Fünf Effekte (Konstant, Pulsieren, Rotieren, Welle, Regenbogen), danach wird die vorherige Beleuchtung wiederhergestellt. Komplett optional und standardmäßig aus.

### Insights

Brabbel misst jedes Diktat: Wartezeit nach der Aufnahme, Anteile von Erkennung, Überarbeitung und Einfügen, Sprechtempo, gesparte Tippzeit. Die **Hardware**-Seite vergleicht Modelle, Engines und Geräte auf deinem Rechner und gibt konkrete Tipps, etwa wann ein größeres Modell kaum langsamer wäre. Gespeichert werden nur Zeiten und Zähler, nie Diktattexte.

### Weitere Details

- **Medien pausieren**: Spotify, Browser oder Media Player werden beim Aufnahmestart angehalten und danach fortgesetzt.
- **Drei Einfügewege**: Tippen (Standard, unter einer Sekunde für lange Texte), Langsam tippen für zickige Programme, Zwischenablage mit Wiederherstellung des vorherigen Inhalts.
- **Ressourcen im Blick**: Unter **System → Ressourcen** siehst du, was Whisper und Textmodell an RAM und VRAM belegen, und kannst sie entladen.
- **Suche in den Einstellungen**: Jede Option ist über das Suchfeld direkt erreichbar. Änderungen werden sofort gespeichert.
- **Autostart** mit Windows, ohne Adminrechte.

## Systemanforderungen

| | Minimum | Empfohlen |
| --- | --- | --- |
| Betriebssystem | Windows 10 (Version 2004) oder Windows 11, 64 Bit | Windows 11 |
| Arbeitsspeicher | 8 GB | 16 GB für die Textüberarbeitung |
| Grafikkarte | keine, Verarbeitung auf CPU | NVIDIA (CUDA) oder AMD / Intel mit Vulkan-1.2-Treiber |
| Speicherplatz | ca. 1 GB plus gewähltes Modell | 3 bis 6 GB mit großem Modell, GPU-Laufzeit und Textmodell |
| Sonstiges | Mikrofon, Mikrofonzugriff für Desktop-Apps in den Windows-Datenschutzeinstellungen | |

Python muss nicht installiert werden. Administratorrechte braucht nur der optionale PawnIO-Treiber für die RGB-Steuerung mancher Mainboards.

### GPU-Beschleunigung

| Hardware | Spracherkennung | Textüberarbeitung |
| --- | --- | --- |
| NVIDIA | faster-whisper + CUDA 12 | llama.cpp + CUDA |
| AMD / Intel | whisper.cpp + Vulkan | llama.cpp + Vulkan |
| Ohne GPU | faster-whisper auf CPU | llama.cpp auf CPU |

Die GPU-Pakete werden im Setup angeboten oder später in den Einstellungen nachinstalliert. Grafiktreiber installiert Brabbel nicht. Im Modus **Automatisch** fällt Brabbel bei GPU-Fehlern für die Sitzung auf CPU zurück und schreibt den Grund ins Protokoll. Die Vulkan-Laufzeit hält das Modell als lokalen Server im Speicher, sodass jedes Diktat nur noch eine Anfrage an `127.0.0.1` ist.

## Deine Daten

- **Kein Cloud-Dienst.** Aufnahmen, Transkripte und Kontexttexte gehen an keinen Transkriptions- oder KI-Dienst.
- **Keine Telemetrie.** Brabbel sendet keine Nutzungsdaten.
- **Internet nur auf Klick.** Für Modelldownloads, GPU-Pakete und die Updateprüfung. Die automatische Updateprüfung beim Start ist standardmäßig aus.
- **Alles an einem Ort.** Einstellungen, Modelle, Historie und Protokolle liegen unter `%LOCALAPPDATA%\Brabbel`. Die Historie ist abschaltbar und löschbar.
- **Protokolle ohne Inhalt.** Das Log enthält Zeiten, Geräte und Fehler, aber nie diktierten Text.

## Updates

Neue Versionen erscheinen unter [Releases](https://github.com/Seb88123/brabbel-releases/releases). In der App prüfst du über **Tray → Nach Updates suchen** oder **Einstellungen → System**.

- Download und Installation bestätigst du selbst. Während einer Aufnahme wird nie aktualisiert.
- Brabbel prüft die Ed25519-Signatur der Update-Metadaten sowie Größe und SHA-256-Summe des Installers. Manipulierte Downloads werden nicht ausgeführt.
- Ein Update ersetzt nur die Programmdateien. Einstellungen, Historie, Modelle und GPU-Pakete bleiben erhalten.
- Bei einem Fehler stellt der Installer die vorherige Version wieder her.

Die Dateien `update.json` und `update.sig` in den Releases gehören zur Updatefunktion und müssen nicht manuell heruntergeladen werden. Die „Source code“-Archive von GitHub sind keine Installationspakete.

## Bekannte Grenzen

- Windows blockiert Eingaben in Programme, die mit Administratorrechten laufen, und auf dem sicheren Desktop. Für solche Fenster muss Brabbel selbst mit denselben Rechten gestartet werden.
- Das bei Aufnahmestart aktive Fenster muss beim Einfügen noch aktiv sein. Bei einem Fensterwechsel bleibt der Text in der Schnell-Historie verfügbar.
- Programme mit eigenen Eingabemechanismen können Unicode-Eingaben ignorieren. Dann hilft der Einfügeweg **Zwischenablage**.
- Die Vulkan-Spracherkennung verwendet einen fest versionierten, SHA-256-geprüften [Community-Build von whisper.cpp](https://github.com/jerryshell/whisper.cpp-windows-vulkan-bin). Ein offizielles Windows-Vulkan-Paket gibt es derzeit nicht.
- ASUS Aura Sync überschreibt die Aufnahmefarbe auf Mainboards laufend. Brabbel erkennt den Dienst und weist darauf hin.
- Der Installer ist nicht mit einem Windows-Codesignaturzertifikat signiert; SmartScreen zeigt beim ersten Start eine Warnung.

## Fragen, Fehler, Ideen

- **Fehler melden**: In der App über **Tray → Feedback & Fehler melden**. Brabbel stellt Version, Windows-Build, GPU, Engine, Modell und die letzten Protokollzeilen zusammen. Du siehst den Bericht vor dem Absenden und kannst ihn bearbeiten. **Auf GitHub melden …** öffnet ein vorausgefülltes [Issue](https://github.com/Seb88123/brabbel-releases/issues).
- **Wünsche und Ideen**: Ebenfalls über den Feedback-Dialog oder direkt als [Issue](https://github.com/Seb88123/brabbel-releases/issues/new/choose).
- **Fragen zur Bedienung**: In den [Discussions](https://github.com/Seb88123/brabbel-releases/discussions).

Bitte keine vertraulichen Diktate oder persönlichen Inhalte in Issues veröffentlichen.

## Lizenz und Drittkomponenten

Brabbel steht unter der **GNU General Public License v3.0 oder später**. Der Quellcode wird separat entwickelt; dieses Repository enthält die Downloads und Versionshinweise.

Brabbel baut auf großartiger Open-Source-Arbeit auf: Whisper (OpenAI), [faster-whisper](https://github.com/SYSTRAN/faster-whisper) und CTranslate2, [whisper.cpp](https://github.com/ggml-org/whisper.cpp) und [llama.cpp](https://github.com/ggml-org/llama.cpp), Qwen3 (Alibaba), Silero VAD, [OpenRGB](https://openrgb.org), Qt for Python, PortAudio. Nachgeladene Programme und Modelle werden mit ihren Lizenztexten unter `%LOCALAPPDATA%\Brabbel` abgelegt.

Whisper, OpenRGB, Logitech, G HUB, ASUS, Aura, NVIDIA, CUDA, Vulkan und Windows sind Marken ihrer jeweiligen Inhaber und werden hier nur zur Beschreibung der Kompatibilität genannt.
