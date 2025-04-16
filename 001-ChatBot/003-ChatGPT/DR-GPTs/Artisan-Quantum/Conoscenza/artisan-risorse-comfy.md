# Guida ComfyUI – Installazione, Prompt e Integrazione

## 1. Introduzione
ComfyUI è una GUI node-based per Stable Diffusion che consente il controllo avanzato del processo di generazione di immagini AI. È altamente modulare, personalizzabile e adatta a flussi di lavoro professionali.

## 2. Installazione di ComfyUI (locale)

### Requisiti:
- Python 3.10 o superiore
- Git
- GPU NVIDIA con supporto CUDA (opzionale ma consigliato)

### Procedura:
1. Clona il repository:
```
git clone https://github.com/comfyanonymous/ComfyUI.git
cd ComfyUI
```
2. Crea ambiente virtuale (opzionale ma consigliato):
```
python -m venv venv
venv\Scripts\activate  (Windows)
source venv/bin/activate  (macOS/Linux)
```
3. Installa le dipendenze:
```
pip install -r requirements.txt
```
4. Avvia ComfyUI:
```
python main.py
```
5. Accedi all’interfaccia:
```
http://127.0.0.1:8188/
```

## 3. Concetti di base
- Nodi principali: Load Checkpoint, KSampler, CLIP Text Encode, VAE Encode/Decode
- Prompt: inseriti tramite nodi `CLIP Text Encode` o `Positive / Negative Prompt`
- Output: immagini salvate automaticamente o visualizzate via nodo `Image Viewer`

## 4. Prompting avanzato
- Utilizza prompt strutturati in lingua naturale (es. "A serene landscape at sunset, volumetric lighting")
- Supporta prompt multipli (es. `Prompt Schedule` o `Prompt Interpolation`)
- Integra LoRA e ControlNet tramite nodi specifici
- Può usare varianti di pipeline: SD1.5, SDXL, Anime, RealisticVision, ecc.

## 5. Integrazione via API

### Invio di prompt da applicazioni esterne:
Endpoint API:
```
POST http://127.0.0.1:8188/prompt
```
Payload JSON:
```json
{
  "prompt": { ... },
  "client_id": ""  
}
```

### Ricezione output
- Ricevi percorso immagine nel JSON di risposta
- Visualizza l'immagine via URL locale o caricala in software esterni (es. TouchDesigner, web app)

## 6. Strumenti e estensioni
- ComfyUI Manager: per installare nodi custom, LoRA, modelli
- Comfyroll: preset e macro per flussi di lavoro rapidi
- ComfyUI-Impact Pack: libreria di nodi avanzati (composizione, effetti, AI blending)
- ComfyUI-Custom-Node: nodi community per automazione, scripting, randomizzazione

## 7. Risorse utili
- GitHub ufficiale: https://github.com/comfyanonymous/ComfyUI
- Wiki community: https://github.com/comfyanonymous/ComfyUI/wiki
- Discord ComfyUI: https://discord.gg/comfyui
- Repository nodi: https://github.com/ltdrdata/ComfyUI-Manager
- YouTube (guide e workflow): https://www.youtube.com/@comfyui
- Stable Diffusion Art – guida e reference prompts: https://stable-diffusion-art.com/

## 8. Idee di utilizzo creativo
- Generazione immagini sincrona da TouchDesigner (prompt dinamici)
- Creazione batch da CSV o dataset
- Prompt evolutivi generati da input MIDI, audio o sensori
- Creazione di video AI interpolati (frame-to-frame)

Fine della guida.