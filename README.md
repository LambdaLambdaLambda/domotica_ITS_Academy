# Arduino: piattaforma hardware e software

Panoramica sintetica basata sulla pagina ufficiale del software Arduino.

![Arduino IDE](https://www.arduino.cc/wiki/static/ide-a6b6a068e29663bfde50923fc52fb982.svg)
![Arduino Cloud Editor](https://www.arduino.cc/wiki/static/cloud-editor-a98c1c506f34b5017373feae973d89bf.png)

## Cos'e la piattaforma hardware Arduino
Arduino usa schede (board) su cui si caricano gli sketch. Gli strumenti software ufficiali consentono di programmare e caricare il codice sulla board collegata, sia da desktop sia dal browser.

## Arduino IDE (desktop)
- La pagina Software indica la release Arduino IDE 2.3.7.
- L'IDE include un editor moderno, un'interfaccia piu reattiva, autocompletion, code navigation e un debugger live.
- L'IDE 2.0 e open source con codice sorgente ospitato su GitHub.

## Dove scaricare l'IDE
- Download dalla pagina Arduino Software tramite i pulsanti "Download".
- Sono disponibili anche Nightly Builds (anteprime con funzionalita e bugfix piu aggiornati) e la versione Legacy IDE 1.8.19.

## Sviluppo in cloud
- Arduino Cloud Editor: IDE online per scrivere, caricare e accedere ai progetti dal browser, gratuitamente.
- Arduino Cloud on Chromebook: app per programmare online, salvare gli sketch nel cloud e caricarli sulla board collegata; librerie incluse automaticamente e nuove board supportate out of the box.

## Come funziona in generale Arduino
In pratica si scrivono sketch, si gestiscono librerie e board e si caricano i progetti sulla scheda con strumenti diversi a seconda del contesto. L'ecosistema ufficiale include anche:
- Arduino CLI: interfaccia a riga di comando per build/compile/upload di sketch e gestione di librerie e board.
- Arduino Lab for MicroPython: editor leggero con connessione alla board, upload, trasferimento file e REPL interattiva.
- Arduino App Lab: ambiente visuale per la board UNO Q con moduli "Bricks" e supporto a modelli AI; supporta sketch C++ via Arduino IDE e Python.
- Arduino PLC IDE: sviluppo con linguaggi IEC 61131-3 e integrazione di sketch Arduino con strumenti di debug.

## Servizi di connessione remota (terzi)
Esempi di strumenti usati per accesso e supporto a distanza di computer o dispositivi collegati ai progetti:
- TeamViewer: software di accesso e supporto remoto per collegarsi a dispositivi da qualsiasi luogo.
- Tailscale: servizio di accesso remoto che crea una rete privata sicura tra dispositivi, utile per collegarsi in modo semplice senza VPN tradizionali.

## Fonti
Testo: https://www.arduino.cc/en/software/
Servizi di connessione remota:
- https://www.teamviewer.com/en-us/products/teamviewer/
- https://tailscale.com/use-cases/remote-access/
Immagini:
- https://www.arduino.cc/wiki/static/ide-a6b6a068e29663bfde50923fc52fb982.svg
- https://www.arduino.cc/wiki/static/cloud-editor-a98c1c506f34b5017373feae973d89bf.png
