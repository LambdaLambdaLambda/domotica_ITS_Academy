# Progetto integrato Arduino + Jetson + Camera (6 gruppi)

Questo documento spiega come organizzare il lavoro dei 6 gruppi e quali risultati produrre.

## Obiettivo del progetto
Realizzare un sistema in cui:
- Arduino legge un sensore e invia i dati via seriale alla Jetson.
- Jetson legge i dati del sensore e i frame della camera USB.
- Al verificarsi di una condizione sul dato del sensore, Jetson salva il frame della camera.
- Un web server Python (Flask) registra i dati in un database (valore sensore, data/ora, path immagine).
- Il server espone una pagina web con i dati e le immagini salvate.
- Il server espone una Web API CRUD (HTTP con metodi GET/POST/PUT/DELETE).
- Jetson ha TeamViewer installato per accesso remoto.
- Su Jetson gira un processo demone che avvia i servizi e gestisce l'avvio/arresto.

## Organizzazione in gruppi
Sono previsti 6 gruppi, divisi in 3 coppie. Ogni coppia lavora su una Jetson.

### Dotazione per ogni coppia
- 1 NVIDIA Jetson Orin Nano + 1 camera USB
- 1 Arduino UNO con sensore (dal kit)
- 1 PC del laboratorio

### Ruoli in ogni coppia
**Gruppo A (Arduino + Remote + Client):**
- Programma Arduino e collega il sensore.
- Definisce il protocollo seriale con il Gruppo B.
- Installa e configura TeamViewer sul PC di laboratorio (per accesso remoto alla Jetson).
- Prepara strumenti CLI per testare la Web API (curl o altri).

**Gruppo B (Jetson + Server):**
- Installa e configura software su Jetson (TeamViewer, Python, librerie, driver camera).
- Implementa lettura seriale, acquisizione camera e salvataggio immagini.
- Implementa web server Flask, database e Web API CRUD.
- Configura un servizio (systemd) per avvio automatico.

## Specifiche da concordare (documenti obbligatori)
Ogni coppia deve produrre 2 documenti condivisi e firmati da entrambi i gruppi:

1. **Specifica protocollo seriale**
   - Baud rate (es. 9600 o 115200)
   - Formato messaggio (es. `SENSOR:<valore>\n`)
   - Unita di misura e range attesi
   - Strategie di errore (checksum, retry, valori invalidi)

2. **Specifica Web API**
   - Endpoint e metodi HTTP
   - Formato JSON richieste/risposte
   - Codici di errore e messaggi

## Architettura logica (riassunto)
- **Arduino** -> invia stringhe seriali con il valore sensore
- **Jetson** -> legge seriale + camera, salva immagine se condizione = true
- **Jetson** -> server Flask con pagina web e API CRUD
- **Database** -> salva record: id, timestamp, valore sensore, path immagine

## Scelta sensore (esempi consigliati)
- LDR (fotoresistenza) per soglia luce
- TMP36 per soglia temperatura
- Potenziometro per soglie manuali

## Requisiti minimi software su Jetson
- Ubuntu + Python 3
- Flask
- Libreria per camera (OpenCV consigliato)
- Libreria per seriale (pyserial)
- SQLite (o altro DB semplice)
- TeamViewer
- systemd service

## Fasi di lavoro consigliate
1. **Accordo specifiche** (protocollo seriale + Web API)
2. **Arduino**: lettura sensore + invio seriale
3. **Jetson**: ricezione seriale + logging console
4. **Jetson**: acquisizione camera + salvataggio immagine
5. **Jetson**: database + web server Flask
6. **Web API CRUD** + pagina web
7. **Test integrato** Arduino -> Jetson -> DB -> pagina web
8. **Attivazione daemon** (systemd) + test riavvio

## Indicazioni per il protocollo seriale (esempio)
Formato semplice, una riga per campione:

```
SENSOR:123\n
```

Regole:
- Il valore e' un intero o float
- Ogni riga termina con `\n`
- Se il dato e' invalido, inviare `SENSOR:NaN`

## Indicazioni per la Web API (esempio)
Base URL: `http://<IP_JETSON>:5000/api`

- `POST /records` crea record
- `GET /records` lista record
- `GET /records/<id>` dettaglio record
- `PUT /records/<id>` modifica record
- `DELETE /records/<id>` elimina record

### Esempio JSON
```
{
  "timestamp": "2026-02-12T14:30:00Z",
  "sensor_value": 123.4,
  "image_path": "static/captures/img_20260212_143000.jpg"
}
```

## Pagina web (requisito)
La pagina deve mostrare:
- Tabella con data/ora e valore sensore
- Immagine associata (thumbnail o link)
- Aggiornamento manuale (refresh)

## TeamViewer (requisito)
- Jetson deve avere TeamViewer installato
- Il PC del laboratorio deve potersi connettere alla Jetson
- Annotare ID e nome host nel documento di consegna

## Avvio automatico (systemd)
- Creare un servizio che avvia lo script Python all'avvio
- Il servizio deve poter essere riavviato con `systemctl restart`
- Log consultabile con `journalctl -u <nome-servizio>`

## Deliverable finali (per ogni coppia)
- Documento protocollo seriale
- Documento Web API
- Codice Arduino (sketch)
- Codice Python Jetson
- Screenshot pagina web con dati reali
- Breve relazione di test (cosa funziona / cosa no)

## Suggerimenti di test
- Simulare soglia sensore variando luce/temperatura
- Controllare che l'immagine salvata corrisponda al trigger
- Verificare che il DB contenga record con timestamp corretto
- Testare la Web API con `curl`
