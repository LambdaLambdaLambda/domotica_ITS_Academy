# Modulo 2 - Reti e Comunicazione

## Obiettivo del modulo
Imparare i fondamenti di comunicazione tra dispositivi (seriale e wireless) e i protocolli usati nei sistemi IoT e nei sistemi industriali.

## Contenuti
- Protocolli di comunicazione seriali (UART, I2C)
- Comunicazione wireless (WiFi, Bluetooth)
- Protocolli IoT (MQTT, HTTP/REST, WebSocket)
- Web servers in Flask
- Topologie di rete per sistemi industriali
- Configurazione connessioni di rete
- Indirizzamento IP statico e dinamico

## Spiegazioni dei contenuti
- Protocolli di comunicazione seriali (UART, I2C): come collegare sensori e moduli con bus semplici, affidabili e a bassa velocita.
- Comunicazione wireless (WiFi, Bluetooth): differenze di raggio, banda, consumi e scenari d'uso tipici.
- Protocolli IoT (MQTT, HTTP/REST, WebSocket): publish/subscribe vs request/response e impatto su latenza e scalabilita.
- Web servers in Flask: creare un endpoint minimo per visualizzare dati e ricevere comandi.
- Topologie di rete per sistemi industriali: stella, bus, mesh e reti ibride con pro e contro su affidabilita e manutenzione.
- Configurazione connessioni di rete: SSID, sicurezza, porte e firewall di base per evitare accessi indesiderati.
- Indirizzamento IP statico e dinamico: quando usare DHCP e quando fissare un IP per accesso remoto stabile.

## Cosa saprai fare alla fine
- Configurare una comunicazione seriale tra sensore e microcontrollore
- Pubblicare e leggere dati tramite MQTT o HTTP
- Esporre un endpoint HTTP minimale con Flask
- Comprendere differenze tra rete cablata, wireless e topologie miste

## Link utili
- Arduino Language Reference (Serial, Wire, SPI): https://docs.arduino.cc/language-reference/
- MQTT Specification: https://mqtt.org/mqtt-specification/
- HTTP overview (MDN): https://developer.mozilla.org/en-US/docs/Web/HTTP/Overview
- WebSocket Protocol (RFC 6455): https://www.rfc-editor.org/rfc/rfc6455
- Flask Quickstart: https://flask.palletsprojects.com/en/stable/quickstart/
