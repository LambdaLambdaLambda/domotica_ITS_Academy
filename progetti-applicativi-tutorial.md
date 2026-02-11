# Tutorial - Progetti applicativi specifici

Questa guida trasforma i due progetti applicativi del corso in un percorso operativo, dalla definizione dei requisiti al collaudo.

## Materiali hardware minimi (per gruppo 4-5 studenti)
- 1x Arduino MEGA con kit sensori
- 1x Raspberry Pi 4 con SD card e alimentatore
- 1x Webcam USB o modulo camera (opzionale se serve visione)
- Sensori: sensore fotoelettrico, encoder rotativo
- Attuatori: LED, buzzer
- Breadboard, cavi jumper, alimentatori
- Router WiFi per connessione

## Metodo di lavoro consigliato
1. Definisci requisiti e soglie operative (range, allarmi, tempi di campionamento).
2. Disegna l'architettura: sensori e attuatori su Arduino, gateway e dashboard su Raspberry Pi.
3. Implementa prima la lettura dei sensori, poi la logica di controllo, infine la parte di rete.
4. Prepara un logging dati continuo e una dashboard essenziale.
5. Valida con scenari reali o simulati e documenta il comportamento.

## Progetto 1 - Monitoraggio Fermentazione (Vino/Birra)

### Obiettivo
Raccogliere dati multi-sensore e controllare in modo automatico la temperatura durante la fermentazione.

### Requisiti funzionali
- Multi-sensore: temperatura, pH, pressione, CO2
- Logging dati continuo
- Curve di fermentazione
- Controllo temperatura con feedback
- Allarmi automatici per anomalie
- Controllo valvole degasaggio
- Dashboard web real-time

### Passi operativi
1. Mappa le variabili di processo (T, pH, pressione, CO2) e le soglie di allarme.
2. Collega i sensori ad Arduino e definisci il sampling rate.
3. Invia i dati a Raspberry Pi via seriale o MQTT.
4. Salva i dati in CSV o in un database time-series.
5. Implementa un controllo temperatura semplice (on/off o PWM) e il controllo delle valvole.
6. Crea una dashboard web (Flask) con grafici aggiornati in tempo reale.
7. Testa gli allarmi con dati simulati e registra le curve di fermentazione.

## Progetto 2 - Sicurezza Alimentare

### Obiettivo
Rilevare condizioni di rischio ambientale e difetti nel confezionamento.

### Requisiti funzionali
- Rilevamento livelli di ammoniaca nell'aria
- Ventilazione automatica di emergenza
- Rilevamento di oggetti metallici nelle bottiglie

### Passi operativi
1. Identifica i sensori per ammoniaca e i livelli soglia di sicurezza.
2. Integra un attuatore per la ventilazione automatica (ventola o relè).
3. Configura il sensore per rilevamento metalli o presenza oggetti.
4. Implementa una logica di allarme locale (LED/buzzer) e remota (notifica dashboard).
5. Registra gli eventi di allarme e le attivazioni della ventilazione.
6. Esegui prove di validazione con scenari controllati.

## Link utili
- Arduino Documentation: https://docs.arduino.cc/
- Raspberry Pi Documentation: https://www.raspberrypi.com/documentation/
- MQTT Specification: https://mqtt.org/mqtt-specification/
- Flask Quickstart: https://flask.palletsprojects.com/en/stable/quickstart/
