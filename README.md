# TonUINO LOLIN32
Die DIY Musikbox (nicht nur) für Kinder

## Wichtig!
Der aktuelle Fritzing PCB Entwurf hat folgendes Problem:
Höhere Lautstärken beim DFPlayer sorgen dafür, dass die 3.3V Spannung kurz einbricht und der DFPlayer abstürzt und SEHR laute Geräusche von sich gibt. Dies kann auch passieren wenn die Ladespannung unterbrochen wird.
Es muss unbedingt die Spannungsversorgung durch ein DC/DC Modul der DFPlayer mit 5V versorgt werden. Kleinere Module können direkt auf die Platine unter den Lolin32 gesetzt werden und müssen dann durch freie Verdrahtung angeschlossen werden.


# Change Log

## Version 2.1 LOLIN32 MOD WIP
- Diverse Anpassungen, damit der Code auf einem ESP32 läuft
- Standby mit Aufweckfunktion über Taste (LOLIN32)
- Vorbereitung für einen P-MOSFET zur Abschalltung des DFPlayers / LEDs / Beschleunigungssensors
- Schlagerkennung um zum nächsten Titel zu springen (wie Toniebox)
- 4-Wire LEDs - FastLED Anbindung (2 LEDs mit LPD8806 implementiert)
- Kopfhörererkennung und automatische Umschaltung
- Fritzing Vorlage für Platine (Kompakt, passt in Toniebox)
- Spannungsteiler USB (Akku wird geladen) / Spannungsteiler Akku (Abschaltung Akku leer) -> Nur Hardware

## Version 2.1 (xx.xx.xxxx) noch WIP
- Partymodus hat nun eine Queue -> jedes Lied kommt nur genau 1x vorkommt
- Neue Wiedergabe-Modi "Spezialmodus Von-Bis" - Hörspiel, Album und Party -> erlaubt z.B. verschiedene Alben in einem Ordner zu haben und je mit einer Karte zu verknüpfen
- Admin-Menü
- Maximale, Minimale und Initiale Lautstärke
- Karten werden nun über das Admin-Menü neu konfiguriert
- die Funktion der Lautstärketasten (lauter/leiser oder vor/zurück) kann im Adminmenü vertauscht werden
- Shortcuts können konfiguriert werden!
- Support für 5 Knöpfe hinzugefügt
- Reset der Einstellungen ins Adminmenü verschoben
- Modikationskarten (Sleeptimer, Tastensperre, Stopptanz, KiTa-Modus)
- Admin-Menü kann abgesichert werden

## Version 2.01 (01.11.2018)
- kleiner Fix um die Probleme beim Anlernen von Karten zu reduzieren

## Version 2.0 (26.08.2018)

- Lautstärke wird nun über einen langen Tastendruck geändert
- bei kurzem Tastendruck wird der nächste / vorherige Track abgespielt (je nach Wiedergabemodus nicht verfügbar)
- Während der Wiedergabe wird bei langem Tastendruck auf Play/Pause die Nummer des aktuellen Tracks angesagt
- Neuer Wiedergabemodus: **Einzelmodus**
  Eine Karte kann mit einer einzelnen Datei aus einem Ordner verknüpft werden. Dadurch sind theoretisch 25000 verschiedene Karten für je eine Datei möglich
- Neuer Wiedergabemodus: **Hörbuch-Modus**
  Funktioniert genau wie der Album-Modus. Zusätzlich wir der Fortschritt im EEPROM des Arduinos gespeichert und beim nächsten mal wird bei der jeweils letzten Datei neu gestartet. Leider kann nur der Track, nicht die Stelle im Track gespeichert werden
- Um mehr als 100 Karten zu unterstützen wird die Konfiguration der Karten nicht mehr im EEPROM gespeichert sondern direkt auf den Karten - die Karte muss daher beim Anlernen aufgelegt bleiben!
- Durch einen langen Druck auf Play/Pause kann **eine Karte neu konfiguriert** werden
- In den Auswahldialogen kann durch langen Druck auf die Lautstärketasten jeweils um 10 Ordner oder Dateien vor und zurück gesprungen werden
- Reset des MP3 Moduls beim Start entfernt - war nicht nötig und hat "Krach" gemacht
