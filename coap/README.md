## CoAP (Constrained Application Protocol)
***

> [⇧ **Home**](https://github.com/iotkitv4/intro)

![](https://raw.githubusercontent.com/iotkitv4/intro/main/images/COAPRD.png) 

Object Model

- - -

![](https://raw.githubusercontent.com/iotkitv4/intro/main/images/M2MObject.png) 

M2M Location Object mit 6 Ressourcen

Quelle: [OMA Lightweight M2M Tutorial](http://de.slideshare.net/zdshelby/oma-lightweightm2-mtutorial)

- - -
[Constrained Application Protocol (CoAP)](http://en.wikipedia.org/wiki/Constrained_Application_Protocol) ist ein Software-Protokoll welches für Internet der Dinge Geräte zugeschnitten ist.

CoAP ist auf den meisten Geräten, die UDP Unterstützen, lauffähig.

Ein CoAP fähiges Gerät publiziert seine Sensoren und Aktoren in einem Resource Directory oder stellt selber ein solches zur Verfügung.

Mittels Resource Discovery können die vorhandenen Sensoren und Aktoren mit ihren Attributen abgefragt werden.

Standardmässig sind folgende **Standard Device Management Objects** vorhanden

*   1 - Server
*   2 - Zugriffsberechtigungen
*   3 - Gerät
*   4 - Monitoring
*   5 - Firmware
*   6 - GPS Informationen

Komplettes Verzeichnis: [OMNA Lightweight M2M (LWM2M) Object & Resource Registry](http://www.openmobilealliance.org/wp/omna/lwm2m/lwm2mregistry.html)

### Beispiel(e)

Ein Beispiel inkl. Anleitung findet man auf [Pelion](https://developer.pelion.com/guides/connect-device-to-pelion/), welches in mbed integriert ist.

### Links 

*   [Office Hours - Pelion Device Management - Connect Service](https://www.youtube.com/watch?v=HUJcAscT5-s)
* 	[ARM CoAP YouTube Tutorial](https://www.youtube.com/watch?v=4bSr5x5gKvA&list=PLgyFKd2HIZlZNsrWXyE4kgLDo_tyLpvDW&index=7)
* 	[Eclipse Leshan YouTube Tutorial](https://www.youtube.com/watch?v=KZEi-Q7_EL0)
*   [ARM CoAP Tutorial](http://community.arm.com/servlet/JiveServlet/previewBody/8633-102-2-15471/ARM%20CoAP%20Tutorial%20April%2030%202014.pdf)
*   [mbed Client](https://github.com/ARMmbed/mbed-os-example-pelion)
*   [RFC 7252- COAP](https://tools.ietf.org/html/rfc7252)
*   [RFC 6690 - Constrained RESTful Environments (CoRE) Link Format](https://tools.ietf.org/html/rfc6690)
*   [RFC 5988 - Web Linking](https://tools.ietf.org/html/rfc5988)
* 	[NodeJS Coap Server](https://github.com/mcollina/node-coap)
* 	[NodeJS Coap CLI](https://www.npmjs.com/package/coap-cli)
*   [Building an internet connected lighting system](https://docs.mbed.com/docs/building-an-internet-connected-lighting-system/en/latest/)

