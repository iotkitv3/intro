Software
--------
***

> [⇧ **Home**](../README.md)

### Inhaltsverzeichnis

* [Betriebssystem](#betriebssystem)
* [Entwicklungsumgebungen](#entwicklungsumgebungen)
    * [Arm Mbed Studio (empfohlen)](https://os.mbed.com/docs/mbed-studio/current/introduction/index.html)
    * [Arm Mbed Online Compiler](https://os.mbed.com/docs/mbed-os/latest/quick-start/build-with-the-online-compiler.html)
    * [mbed CLI](https://os.mbed.com/docs/mbed-os/v6.6/build-tools/mbed-cli-2.html) - nur für Erfahrene Nutzer
* [Beispiele](#beispiele)
* [Serielle Kommunikation](#serielle-kommunikation) **wird für Ausgabe von Debug Informationen benötigt!**

## Betriebssystem
***

> [⇧ **Nach oben**](#inhaltsverzeichnis)

![](https://os.mbed.com/docs/mbed-os/v6.6/introduction/images/Mbed_OS_diagram_for_intro.png)

Architekturdiagramm mbed OS
- - -

Der IoTKit V3 verwendet [ARM mbed OS](https://www.mbed.com/en/platform/mbed-os/).

ARM mbed OS ist ein Open-Source-Embedded-Betriebssystem, das speziell für die "Dinge" im Internet der Dinge entwickelt wurde.

Es enthält alle Funktionen, die benötigt werden, um ein angeschlossenes Produkt auf Basis eines ARM Cortex-M Mikrocontrollers zu entwickeln, einschliesslich Sicherheit, Konnektivität, RTOS und Treiber für Sensoren und E / A-Geräte.

## Entwicklungsumgebungen
***

> [⇧ **Nach oben**](#inhaltsverzeichnis)

![](https://os.mbed.com/docs/mbed-studio/current/getting-started/images/new_blinky.gif)

Quelle: https://os.mbed.com/docs/mbed-studio/current/getting-started/index.html
- - - 

Als Entwicklungsumgebung wird das [Arm Mbed Studio (empfohlen)](https://os.mbed.com/docs/mbed-studio/current/introduction/index.html) empfohlen.

Meistens werden die [mbed Boards](https://os.mbed.com/platforms/?q=&Mbed+OS+support=Mbed+OS+6.6) automatisch erkannt und es kann sofort [gestartet](https://os.mbed.com/docs/mbed-studio/current/getting-started/index.html) werden.

Das [IoTKitV3 K64F](https://github.com/iotkitv3/intro/tree/main/hw#iotkitv3-k64f) muss manuell eingerichtet werden.

![](https://raw.githubusercontent.com/iotkitv3/intro/main/images/iotkit-k64f-configuration.png)

## Beispiele
***

> [⇧ **Nach oben**](#inhaltsverzeichnis)

![](https://raw.githubusercontent.com/iotkitv3/intro/main/images/ImportProgramm.png)

- - -

Die Beispiele sind in der GitHub Organisation [iotkitv3](https://github.com/iotkitv3) zusammengefasst.

Und können mittels mittels File -> Import Programm importiert werden:

* [GPIO](https://github.com/iotkitv4/gpio)
* [Sensoren](https://github.com/iotkitv4/sensors)
* [Aktoren](https://github.com/iotkitv4/actors)
* [UART](https://github.com/iotkitv4/uart)
* [I²C/TWI](https://github.com/iotkitv4/i2c)
* [SPI](https://github.com/iotkitv4/spi)
* [WLAN (WiFi)](https://github.com/iotkitv4/wlan)
* [HTTP und REST inkl. Node-RED](https://github.com/iotkitv4/http) - (**MBED OS 5**)
* [MQTT inkl. Node-RED](https://github.com/iotkitv4/mqtt)
* [NFC / RFID](https://github.com/iotkitv4/rfid)
* [Cloud Anbindung](https://github.com/iotkitv4/cloud) an Amazon (AWS), Google und Microsoft (Azure).

Jedes Programm enthält eine `main.cpp` Datei mit dem eigentlichen Programm.

Die weiteren Beispiele sind in der Datei `README.md` Beschrieben und können durch Überschreiben des Inhaltes (Copy & Paste) der Datei `main.cpp` ausprobiert werden.

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
* [Integriert in Arm Mbed Studio (empfohlen)](https://os.mbed.com/docs/mbed-studio/current/introduction/index.html)
* [Windows](http://sourceforge.jp/projects/ttssh2/releases/)
* [Mac](http://freeware.the-meiers.org/)
* [Linux](http://manpages.ubuntu.com/manpages/vivid/man8/picocom.8.html)

Alternativ kann das Terminalprogramm vom mbed CLI verwendet werden. Dies wird wie folgt gestartet:

	mbed sterm

**Links**

* [mbed Tutorial](https://os.mbed.com/docs/mbed-os/latest/tutorials/serial-communication.html)
* [UART (Universal Asynchronous Receiver Transmitter)](https://github.com/iotkitv3/uart) 
