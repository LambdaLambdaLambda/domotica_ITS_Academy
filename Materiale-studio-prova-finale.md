# Materiale di Studio per la Prova Finale

## Fondamenti di Sistemi Embedded e IoT

- Introduzione ai sistemi embedded nell'industria agroalimentare
  - Architetture di sistemi IoT per il monitoraggio industriale
  - Differenze tra microcontrollori e microprocessori
- Overview delle piattaforme: Arduino e NVIDIA Jetson
  - Caratteristiche e ambiti di applicazione di ciascuna piattaforma
  - Criteri di scelta della piattaforma in base all'applicazione
- Elettronica di base e sue applicazioni in Arduino:
  - [Power tree](https://docs.arduino.cc/learn/electronics/power-tree/)
  - [Power pins](https://docs.arduino.cc/learn/electronics/power-pins/)
  - [Power consumption](http://docs.arduino.cc/learn/electronics/power-consumption/)

## Comunicazione seriale

- Comunicazione seriale e debugging: monitor seriale, log e diagnostica
  - [UART](https://docs.arduino.cc/learn/communication/uart/)
  - [I2C](https://docs.arduino.cc/learn/communication/wire/)
  - [CANbus](https://docs.arduino.cc/learn/communication/can/)

## Sensori per l'industria agroalimentare

- Sensori di temperatura: applicazioni per fermentazione, cottura e stoccaggio e lettura dei segnali.

## Attuatori e Sistemi di Controllo

- [Controllo PWM](https://support.arduino.cc/hc/en-us/articles/9350537961500-Use-PWM-output-with-Arduino): generazione di segnali per modulare potenza e velocita senza dissipare energia in eccesso.
[Le grandezze elettriche fondamentali](<./Libri di testo/Elettrotecnica Generale ITIS Volta.pdf>) (Capitolo 2)
- [Reti elettriche e connessioni fondamentali](<./Libri di testo/Elettrotecnica Generale ITIS Volta.pdf>) (Capitolo 3)
- [Componenti elettrici fondamentali](<./Libri di testo/Elettrotecnica Generale ITIS Volta.pdf>) (Capitolo 4)
- [Circuiti con più generatori in serie](<./Libri di testo/Elettrotecnica Generale ITIS Volta.pdf>) (Capitolo 5)
- [Risoluzione delle reti a più maglie](<./Libri di testo/Elettrotecnica Generale ITIS Volta.pdf>) (Capitolo 6)

## Reti di calcolatori

- Topologie di rete per sistemi industriali
- Pila [TCP/IP](https://it.wikipedia.org/wiki/Suite_di_protocolli_Internet)
- Indirizzamento IP statico e dinamico
- Protocollo [HTTP](https://it.wikipedia.org/wiki/Hypertext_Transfer_Protocol) e [Web Server](https://en.wikipedia.org/wiki/Web_server)
- Protocolli IoT ([MQTT](https://mqtt.org/mqtt-specification/), [REST](https://it.wikipedia.org/wiki/Representational_state_transfer), [WebSocket](https://en.wikipedia.org/wiki/WebSocket))

## Controllo Remoto e Accesso ai Dispositivi

- Installazione e configurazione [TeamViewer](https://www.teamviewer.com/en-us/products/teamviewer/): setup dell'accesso remoto, pairing del dispositivo e verifica della connessione.
- Accesso remoto sicuro ai dispositivi: autenticazione, permessi e buone pratiche di sicurezza.
- Remote desktop vs [SSH](https://www.openssh.com/manual.html): interfaccia grafica vs riga di comando, vantaggi e limiti in base al caso d'uso.
- Trasferimento file remoto: copie sicure e sincronizzazione tra dispositivi con strumenti dedicati, (es. [Google Drive](https://developers.google.com/drive/api/guides/about-sdk))
- [Tailscale + Flask su NVIDIA Jetson](tutorial-tailscale-jetson-flask.md)

## Programmazione Arduino

- Ambiente di sviluppo [Arduino IDE](https://docs.arduino.cc/software/ide-v2): installazione, struttura del progetto e strumenti principali.
- [Linguaggio C su Arduino](https://docs.arduino.cc/language-reference/)
- Arduino CLI Documentation: <https://docs.arduino.cc/arduino-cli/>
- Arduino Programming (learning paths): <https://docs.arduino.cc/learn/programming/>
- Struttura sketch (setup, loop): ciclo di vita del programma e tempi di esecuzione.
- Gestione I/O digitali e analogici: lettura sensori e pilotaggio attuatori.
- Librerie per sensori comuni: ricerca, installazione e uso di librerie.
- [Timer e interrupt](https://www.maffucci.it/2021/03/04/arduino-interrupts-lezione-2/): gestione eventi e funzioni time-critical.