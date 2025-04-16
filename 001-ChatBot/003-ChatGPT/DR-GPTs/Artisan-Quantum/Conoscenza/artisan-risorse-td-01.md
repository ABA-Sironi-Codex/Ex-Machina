# Guida Patch TouchDesigner – Visuals Modulari e Integrazioni AI/Modular

## 1. Introduzione
Questa guida accompagna passo dopo passo nella creazione di una patch in TouchDesigner capace di generare visuals interattivi, audio-reactive e integrati con sistemi esterni di generazione AI (ComfyUI) o sintesi modulare (VCV Rack).

**Prerequisiti:**
- TouchDesigner (versione 2022+ consigliata)
- Conoscenze base di CHOP, SOP, TOP
- Python attivo in TouchDesigner
- ComfyUI installato in locale
- VCV Rack installato con plugin per MIDI o OSC

---

## 2. Patch reattiva base in TouchDesigner

### Obiettivo: creare una forma geometrica modulata da audio

1. **Crea un cerchio deformabile:**
   - `Circle SOP` → `Noise SOP` → `Transform SOP`
   - Collega a `Geometry COMP`, `Render TOP`, `Null TOP` → `Out TOP`

2. **Input audio:**
   - `Audio File In CHOP` o `Audio Device In CHOP`
   - `Audio Spectrum CHOP` → `Analyze CHOP`

3. **Modulazione della geometria:**
   - Connetti il `Analyze CHOP` al parametro `Amplitude` del `Noise SOP`

4. **Output visivo finale:**
   - `Render TOP` → `Level TOP` → `Window COMP` o `Video Device Out`

---

## 3. Connessione TouchDesigner + ComfyUI

### Obiettivo: inviare prompt e ricevere immagini da ComfyUI

1. **Setup ComfyUI:**
   - Avvia `main.py` o `run_nodemon.bat`
   - Verifica endpoint API su `http://127.0.0.1:8188/prompt`

2. **Invio da TouchDesigner:**
   - `Text DAT`: scrivi prompt JSON
   - `Web Client DAT`:

```python
op('webclient1').request(
    'http://127.0.0.1:8188/prompt',
    method='POST',
    body=op('text1').text,
    headers={'Content-Type': 'application/json'}
)
```

3. **Ricezione immagine:**
   - Carica via `Movie File In TOP` o `Web Client TOP`

4. **Automazione:**
   - Trigger da `Timer CHOP`
   - Modifica dinamica del prompt tramite input CHOP/DAT

---

## 4. Connessione TouchDesigner + VCV Rack

### Modalità 1: MIDI

1. **VCV Rack:**
   - Modulo `MIDI-CC` (via LoopMIDI / IAC)

2. **TouchDesigner:**
   - `MIDI In CHOP` → collega ai parametri visivi

### Modalità 2: OSC

1. **VCV Rack:**
   - Plugin `trowaSoft OSC` → porta 5000

2. **TouchDesigner:**
   - `OSC In CHOP` o `OSC In DAT` → lettura dei valori

---

## 5. Estensioni creative

- Prompt audio-reactive generati da CHOP → ComfyUI
- Fusione di immagini AI + geometrie 3D
- Controllo MIDI real-time di parametri visivi
- Output registrato con `Movie File Out TOP` o in streaming via `NDI`

---

## 6. Risorse utili

- https://docs.derivative.ca/
- https://github.com/comfyanonymous/ComfyUI
- https://vcvrack.com/manual/
- https://github.com/trowaSoft/VCV-Modules

