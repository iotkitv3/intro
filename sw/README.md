Software
--------
***

> [⇧ **Home**](../README.md)

### Inhaltsverzeichnis

* [Betriebssystem](#betriebssystem)
* [Entwicklungsumgebungen](#entwicklungsumgebungen)
    * [Arm Mbed Online Compiler (empfohlen)](#arm-mbed-online-compiler)
    * [mbed-cli](#mbed-cli)
* [Serielle Kommunikation](#serielle-kommunikation) **wird für Ausgabe von Debug Informationen benötigt!**

## Betriebssystem
***

> [⇧ **Nach oben**](#inhaltsverzeichnis)

![](https://s3-us-west-2.amazonaws.com/mbed-os-docs-images/Mbed_OS_diagram_for_intro.png)

Architekturdiagramm mbed OS
- - -

Der IoTKit V3 verwendet [ARM mbed OS](https://www.mbed.com/en/platform/mbed-os/).

ARM mbed OS ist ein Open-Source-Embedded-Betriebssystem, das speziell für die "Dinge" im Internet der Dinge entwickelt wurde.

Es enthält alle Funktionen, die benötigt werden, um ein angeschlossenes Produkt auf Basis eines ARM Cortex-M Mikrocontrollers zu entwickeln, einschliesslich Sicherheit, Konnektivität, RTOS und Treiber für Sensoren und E / A-Geräte.

## Entwicklungsumgebungen
***

> [⇧ **Nach oben**](#inhaltsverzeichnis)

Als Entwicklungsumgebung können folgende Produkte verwendet werden:
* der [Arm Mbed Online Compiler (empfohlen)](https://os.mbed.com/docs/mbed-os/latest/quick-start/online-with-the-online-compiler.html)
* das [mbed CLI](https://os.mbed.com/docs/mbed-os/latest/quick-start/offline-with-mbed-cli.html)

Eine Tabelle unterhalb jedes Beispiels enthält einen Link auf die Online Version oder zeigt an, wie das Programm für das jeweilige Board zu compilieren ist.

**Beispiel** [DigitalOut](../gpio#digitalout)

| Umgebung/Board    | Link/Befehl                      |
| ----------------- | -------------------------------- |
| Online Compiler | [DigitalOut](https://os.mbed.com/compiler/#import:/teams/IoTKitV3/code/DigitalOut/) |
| CLI (IoTKit K64F) | `mbed compile -m K64F --source . --source ../IoTKitV3/gpio/DigitalOut; ` <br> `cp BUILD/K64F/GCC_ARM/template.bin $DAPLINK` |
| CLI (DISCO_L475VG_IOT01A) | `mbed compile -m DISCO_L475VG_IOT01A -f --source . --source ../IoTKitV3/gpio/DigitalOut` |

Die Tabelle ist wie folgt zu lesen:
* **Online Compiler** verweist in der Spalte *Link/Befehl* auf einen Link welcher den [Arm Mbed Online Compiler](https://os.mbed.com/compiler/) öffnet mit einem Dialog um da Beispiel zu importieren.
* **CLI (IoTKit K64F)** zeigt die Befehle in der Spalte *Link/Befehl*, welche benötigt werden um das Beispiel, mittels [mbed CLI](https://github.com/ARMmbed/mbed-cli), zu Compilieren und das fertige Programm auf das IoTKit K64F Board zu kopieren. 
* **CLI (DISCO_L475VG_IOT01A)** zeigt den Befehl in der Spalte *Link/Befehle*, welcher benötigt wird um das Beispiel, mittels [mbed CLI](https://github.com/ARMmbed/mbed-cli), zu Compilieren und das fertige Programm auf das DISCO_L475VG_IOT01A Board zu kopieren.

Bei beiden **CLI** Varianten wird vorausgesetzt, dass das [mbed CLI](https://github.com/ARMmbed/mbed-cli) Installiert wurde und wir uns in der *Bash* Shell im Verzeichnis `template` befinden. 

Bei der **CLI (IoTKit K64F)** Variante muss zusätzlich das Laufwerk mittels der Umgebungsvariable `DAPLINK` gesetzt sein, z.B. `EXPORT DAPLINK=/d` für das Laufwerk D:.

Ist kein Link **Online Compiler** vorhanden, kann das [IoTKit V3 Template](https://os.mbed.com/teams/IoTKitV3/code/template/) verwendet werden. Dabei ist der Inhalt von `main.cpp` mit dem Inhalt des Beispiels zu ersetzen.

**ACHTUNG**: kann der IoTKit K64F nicht mehr Programmiert werden, Upload endet sofort und es erscheint eine Datei `FAIL.TXT`, ist leicht am Encoder zu drehen und das Board ein- und auszustecken.

### Arm Mbed Online Compiler
***

Für die Online-Entwicklung stellt Arm den [Mbed Online Compiler](https://os.mbed.com/docs/mbed-os/latest/quick-start/online-with-the-online-compiler.html) zur Verfügung. Dies ist eine gute Wahl, wenn Sie schnell mit Mbed OS arbeiten möchten.

**IoTKit mit dem PC/Notebook verbinden**

* IoTKit via USB Kabel mit dem PC/Notebook verbinden.
* Account auf [https://os.mbed.com](https://os.mbed.com) anlegen.
* Für das **IoTKitV3 K64F** auf den URL [https://os.mbed.com/platforms/frdm-k64f/](https://os.mbed.com/platforms/frdm-k64f/), für das **DISCO-L475VG-IOT01A** auf [https://os.mbed.com/platforms/ST-Discovery-L475E-IOT01A/](https://os.mbed.com/platforms/ST-Discovery-L475E-IOT01A/) wechseln und `Add to ... Compiler` (rechts unten) anwählen.
* Das erste Programm mittels URL [https://os.mbed.com/teams/IoTKitV3/code/DigitalOut/](https://os.mbed.com/teams/IoTKitV3/code/DigitalOut/) und «Import Comp…» importieren.
* Ein Dialog erscheint – Programm mit Standardeinstellungen, ohne Update Libraries, importieren

**Programm compilieren**

* Wählt links main.cpp an, das Hauptprogramm erscheint im Editor.
* Drückt `Compile` das Programm wird compiliert (übersetzt in Maschinensprache für den ARM Cortex M4 Prozessor).
* Speichert die *.bin Datei auf dem neu erstellten Laufwerk (Mac/Linux = Verzeichnis) ab (je nach Browser ist die Datei im Verzeichnis `Download` und muss mittels Drag&Drop verschoben werden). 
* Drückt die `Reset Taste` (neben USB Anschluss) auf dem IoTKit. Das  Programm wird vom Laufwerk in den Flash des ARM Cortex M4 Prozessors geschrieben.
* Die 4 LEDs auf dem IoTKit sollten jetzt Abwechslungsweise, im Abstand von 0.5 Sekunden, blinken. 
* Ändert den Wert von `warte = 0.5f` auf `1.0f` in `main.cpp` und wiederholt den Vorgang. Was hat sich verändert 

Zusätzlich zum Laufwerk (Mac/Linux = Verzeichnis), wird auch eine Serielle Verbindung zum IoTKit erstellt (siehe Gerätemanager). Über die Serielle Verbindung können z.B. Debugging Meldungen ausgegeben werden.

Für den richtigen Treiber und die zusätzlich benötigte Software siehe [Serielle Kommunikation](#serielle-kommunikation).

### mbed-cli 
***

> [⇧ **Nach oben**](#inhaltsverzeichnis)

Für die Offline-Entwicklung bietet Arm Mbed CLI, ein Befehlszeilentool an. Mbed CLI ist kompatibel mit Windows, Linux und Mac OS. Mbed CLI bietet mehr Optionen, erfordert jedoch etwas mehr Installation.

[mbed cli](https://github.com/ARMmbed/mbed-cli) mit allen Abhängigkeiten (Python, GCC_ARM) wie unter [Installation](https://os.mbed.com/docs/mbed-os/v5.15/quick-start/offline-with-mbed-cli.html) beschrieben, installieren.

*Bash* Shell starten und in ein Verzeichnis, wo die Beispiele abgelegt werden sollen, wechseln, z.B.

    cd /c/
    
Globale Konfigurationen für Board und Compiler setzen.

	mbed config --global TARGET K64F
	mbed config --global TOOLCHAIN GCC_ARM

[IoTKit V3 Template](https://os.mbed.com/teams/IoTKitV3/code/template/) importieren und compilieren

	mbed import http://os.mbed.com/teams/IoTKitV3/code/template/
	cd template
	mbed compile
	
Für das DISCO_L475VG_IOT01A ist der letzte Befehl durch `mbed compile -m DISCO_L475VG_IOT01A -f` zu ersetzen.	Das Kopieren des Programm und der Reset des Boards erfolgt bei diesem Board automatisch.

Nur **IoTKitV3 K64F**:
* Das compiliertes Beispiel Programm befindet sich im Verzeichnis `BUILD/K64F/GCC_ARM` mit Namen `template.bin`. 
* Dieses ist auf das Laufwerk mit Namen `DAPLINK` zu kopieren und der `Reset`-Button zu drücken, z.B. `cp BUILD/K64F/GCC_ARM/template.bin /d/` bzw. `cp BUILD/K64F/GCC_ARM/template.bin $DAPLINK`

Das Compilierte Programm baut eine Verbindung mit dem Internet auf (WLAN Einstellungen siehe `mbed_app.json`) und zeigt die aktuelle Zeit auf dem OLED Display an.
	
Um die IoTKitV3 Beispiele zu compilieren ist das `src` Verzeichnis im `template` Verzeichnis wegzulöschen (wegen Fehler doppelter `main`) und das IoTKitV3 Repository zu clonen.

	rm -rf src
	cd ..
	git clone https://github.com/mc-b/IoTKitV3.git
	
Die jeweiligen Beispiele können dann wie folgt compiliert werden, z.B. DigitalOut, HallSensorAlarm

	cd template
	mbed compile --source . --source ../IoTKitV3/gpio/DigitalOut/
	
oder 
	
	mbed compile --source . --source ../IoTKitV3/cloud/HallSensorAlarm/
	
Um es dann wie, oben beschrieben, auf das Board zu kopieren und dieses zu Reseten. Die jeweiligen Befehle stehen nochmals unterhalb jedes Beispiels unter **Compilieren**.

**Optional** Beispiele für Eclipse aufbereiten

	mbed export -i eclipse_gcc_arm
	
Anschliessend mittels File -> Import -> Existing Projects `template` und `IoTKitV3` als Projekte in Workspace importieren.	

**Hinweise**:
* Ab mbed OS V5.10 ist die ESP8266 Driver Library Bestandteil von mbed OS.
* Als Nachteil für das schnellere Compilieren, ist zu Erwähnen, dass die Programme grösser sind als normal, weil alle Libraries mit verlinkt werden.

## Serielle Kommunikation
***

> [⇧ **Nach oben**](#inhaltsverzeichnis)

Die Kommunikation mit Ihrem Entwicklungsboard ist ein wesentlicher Bestandteil der Programmierung und des Debugging. Terminalanwendungen erleichtern diese Kommunikation. Die Verwendung von Terminalanwendungen ist häufig der zweite Schritt des Debuggings und kann Ihnen mehr Informationen geben als blinkende Lichter.

**Windows serial driver**

Sie können Ihr Board über USB an Ihren Computer anschließen. Dies sollte unter Linux und macOS sofort funktionieren. Für Windows 10 müssen Sie einen Treiber für die serielle Schnittstelle installieren:

* Laden Sie den seriellen [Port-Treiber](http://os.mbed.com/media/downloads/drivers/mbedWinSerial_16466.exe) von Arm Mbed herunter .
* Schließen Sie Ihr Arm Mbed-Gerät über USB an. Es wird als Laufwerk angezeigt.
* Schließen Sie alle Explorer-Fenster mit dem mbed Laufwerk.
* Führen Sie das Installationsprogramm aus. Dies kann einige Zeit dauern, oder es werden einige Warnungen "nicht signierter Treiber" angezeigt.

**Terminalanwendungen verwenden**

Terminalanwendungen laufen auf Ihrem Host-PC. Sie bieten ein Fenster, in dem Ihr Board Informationen ausgeben kann und in das Sie Zeichen eingeben können.

*Serielle Konfiguration: Die Standardeinstellung für die serielle USB-Schnittstelle ist 9600 Baud, 8 Bit, 1 Stoppbit, keine Parität (9600-8-N-1).*

Terminalemulations Programme: 
* [Windows](http://sourceforge.jp/projects/ttssh2/releases/)
* [Mac](http://freeware.the-meiers.org/)
* [Linux](http://manpages.ubuntu.com/manpages/vivid/man8/picocom.8.html)

Alternativ kann das Terminalprogramm vom mbed CLI verwendet werden. Dies wird wie folgt gestartet:

	mbed sterm

**Links**

* [mbed Tutorial](https://os.mbed.com/docs/mbed-os/latest/tutorials/serial-communication.html)
* [UART (Universal Asynchronous Receiver Transmitter)](../uart/) 
