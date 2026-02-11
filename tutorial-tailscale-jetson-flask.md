# Esempio guidato - Tailscale + Flask su NVIDIA Jetson (Ubuntu)

Questo esempio mostra come:
- installare Tailscale su una NVIDIA Jetson con Ubuntu,
- aggiungere il device alla tua tailnet,
- creare un semplice web server Flask (porta 5000),
- accedere alla pagina da un altro device via Tailscale.

## Prerequisiti
- NVIDIA Jetson con Ubuntu e accesso a Internet
- Un account Tailscale
- Un secondo device con Tailscale installato (PC o smartphone)

## 1) Installare Tailscale sulla Jetson

Metodo rapido (script ufficiale):

```bash
curl -fsSL https://tailscale.com/install.sh | sh
```

Metodo manuale (repo APT per Ubuntu):

```bash
sudo apt-get update
sudo apt-get install tailscale
```

Avvia e collega il device alla tailnet (ti verra mostrato un link di login):

```bash
sudo tailscale up
```

Dopo l'autenticazione, verifica l'IP Tailscale (IPv4):

```bash
tailscale ip -4
```

## 2) Creare un web server Flask sulla porta 5000

Crea una cartella di progetto, un virtualenv e installa Flask:

```bash
mkdir jetson-flask
cd jetson-flask
python3 -m venv .venv
. .venv/bin/activate
pip install Flask
```

Crea `app.py` con una semplice landing page:

```python
from flask import Flask

app = Flask(__name__)

@app.route("/")
def index():
    return """
    <!doctype html>
    <html lang="it">
      <head>
        <meta charset="utf-8" />
        <meta name="viewport" content="width=device-width, initial-scale=1" />
        <title>Jetson + Tailscale</title>
      </head>
      <body>
        <h1>Jetson connessa via Tailscale</h1>
        <p>Questa pagina arriva da una Flask app sulla porta 5000.</p>
      </body>
    </html>
    """

if __name__ == "__main__":
    app.run(host="0.0.0.0", port=5000)
```

Avvia il server:

```bash
python3 app.py
```

Nota: Flask usa la porta 5000 di default e puo essere reso raggiungibile in rete con `--host=0.0.0.0`.

## 3) Accedere alla pagina via Tailscale da un altro device

1. Assicurati che l'altro device sia connesso alla stessa tailnet.
2. Sul Jetson, prendi l'IP Tailscale con `tailscale ip -4`.
3. Apri il browser sull'altro device e visita:

```
http://IP_TAILSCALE_JETSON:5000/
```

Se hai MagicDNS attivo, puoi usare anche il nome macchina:

```
http://NOME-JETSON:5000/
```

## Riferimenti utili
- Download e installazione Tailscale su Linux/Ubuntu: https://tailscale.com/download/linux/ubuntu-2004
- Come ottenere l'IP Tailscale (100.x) e concetti di tailnet: https://tailscale.com/kb/1033/ip-and-dns-addresses/
- MagicDNS: https://tailscale.com/kb/1081/magicdns/
- Installazione Flask: https://flask.palletsprojects.com/en/stable/installation/
- Flask Quickstart (app minima e run): https://flask.palletsprojects.com/en/stable/quickstart/
