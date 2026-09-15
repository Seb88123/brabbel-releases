# Brabbel für Windows

**Brabbel drauflos. Der Text kommt trotzdem ordentlich raus.**

Brabbel ist eine kleine Windows-App zum lokalen Diktieren. Hotkey drücken,
sprechen und den erkannten Text direkt in die aktive Anwendung einfügen – etwa
in eine E-Mail, ein Dokument oder ein Chatfenster. Die Spracherkennung läuft auf
deinem eigenen Gerät.

Dieses Repository enthält die öffentlichen Downloads und Versionshinweise.
Der Quellcode wird separat entwickelt und ist hier nicht enthalten.

## Download

**[Zu den Releases](https://github.com/Seb88123/brabbel-releases/releases)**

Öffne das neueste stabile Release und lade unter **Assets** die Datei
**`BrabbelSetup.exe`** herunter. Falls noch kein Release angezeigt wird, ist noch
kein Installationspaket veröffentlicht.

`update.json` und `update.sig` gehören zur eingebauten Updatefunktion und müssen
nicht manuell heruntergeladen werden. Die von GitHub angebotenen
„Source code“-Archive sind keine Installationspakete für Brabbel.

## Erste Schritte

1. `BrabbelSetup.exe` starten und den Installationsschritten folgen.
2. Ein Whisper-Modell auswählen und herunterladen. Optionale GPU-Beschleunigung
   und Textüberarbeitung lassen sich während der Installation auswählen.
3. Brabbel starten und unter **Aufnahme → Mikrofon** das gewünschte Mikrofon prüfen.
4. In ein Textfeld wechseln und **Strg + Win** gedrückt halten.
5. Sprechen und die Tasten loslassen. Brabbel verarbeitet die Aufnahme
   lokal und fügt den Text ein.

Standard ist **Push-to-Talk**: Solange du den Hotkey gedrückt hältst, wird aufgenommen.
Die Hotkeys sind anpassbar. Alternativ lässt sich ein Umschalt-Hotkey einrichten,
der die Aufnahme mit einem Tastendruck startet und mit dem nächsten stoppt.
**Strg + Win + H** öffnet die Schnell-Historie.

Brabbel bleibt im Infobereich der Windows-Taskleiste aktiv. Ein Doppelklick auf
das Symbol öffnet die Einstellungen; über das Kontextmenü kannst du die App beenden.

## Funktionen

- **Lokale Spracherkennung** mit verschiedenen Whisper-Modellen.
- **Umschalten oder Push-to-Talk** über globale Hotkeys.
- **Aufnahme-Overlay** mit Mikrofonpegel und Verarbeitungsstatus.
- **Optionale Textüberarbeitung** mit einem lokalen Sprachmodell, beispielsweise
  zum Glätten, Kürzen oder Formulieren einer E-Mail.
- **Lokale Historie** und Schnellzugriff auf die letzten Diktate.
- **Optionale GPU-Beschleunigung** und RGB-Rückmeldung auf unterstützter Hardware.

## System und Beschleunigung

Benötigt werden Windows 10 oder 11 in 64 Bit, ein Mikrofon und genügend freier
Speicher für App und Modelle. Python muss nicht separat installiert werden.
Für die erstmalige Installation der ausgewählten Komponenten ist Internet nötig.
Die Modellgröße reicht von rund 75 MB bis zu mehreren GB; die optionale
Textüberarbeitung benötigt zusätzlich etwa 2,5 GB Download und weiteren Arbeitsspeicher.

| Hardware | Optionale Beschleunigung |
| --- | --- |
| NVIDIA | CUDA für Spracherkennung und Textüberarbeitung |
| AMD oder Intel mit geeignetem Vulkan-Treiber | Vulkan für Spracherkennung und Textüberarbeitung |
| CPU | Verarbeitung ohne zusätzliche GPU-Pakete |

Die Beschleunigung ist optional und hängt von Grafiktreiber, Grafikspeicher und
Modell ab. Bei kleinen Modellen oder integrierter Grafik kann die CPU schneller
sein. Im Modus **Automatisch** fällt Brabbel bei GPU-Verarbeitungsfehlern auf CPU
zurück. Grafiktreiber werden von Brabbel nicht installiert.

Die Vulkan-Spracherkennung verwendet einen fest versionierten,
SHA-256-geprüften [Community-Build von whisper.cpp](https://github.com/jerryshell/whisper.cpp-windows-vulkan-bin).

## Updates

Neue Versionen findest du hier unter
[Releases](https://github.com/Seb88123/brabbel-releases/releases).
In Versionen mit eingebauter Updatefunktion kannst du außerdem im Tray-Menü
oder unter **Einstellungen → System → Nach Updates suchen** prüfen.

- Die automatische Prüfung beim App-Start ist optional und standardmäßig aus.
- Download und Installation werden von dir bestätigt.
- Brabbel prüft die digitale Update-Signatur und die Prüfsumme des Installers.
- Beim Update bleiben Einstellungen, Historie, Modelle und GPU-Pakete erhalten.

Eine ältere Version ohne Updatefunktion wird zunächst regulär mit dem neuen
Installer aktualisiert.

## Deine Daten

Spracherkennung und optionale Textüberarbeitung laufen lokal. Aufnahmen und
Diktate werden dafür nicht an einen Transkriptionsdienst geschickt.
Modelldownloads und die optionale Updateprüfung benötigen eine Internetverbindung.

Einstellungen, Modelle und die aktivierte Historie liegen unter
`%LOCALAPPDATA%\Brabbel`. Die Historie lässt sich in den Einstellungen deaktivieren
und löschen. Audioaufnahmen werden nicht als Historie archiviert.

## Probleme melden

Fehler und Verbesserungsvorschläge kannst du unter
[Issues](https://github.com/Seb88123/brabbel-releases/issues) melden.
Hilfreich sind die Brabbel-Version, Windows-Version, die verwendete Engine und
eine kurze Beschreibung, wie sich das Problem reproduzieren lässt.
Bitte keine vertraulichen Diktate oder persönlichen Inhalte veröffentlichen.
