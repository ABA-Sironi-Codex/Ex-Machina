---
title: 000 - Introduzione a Stable Diffusion
date: sabato, 07/12/2024
tags:
  - stable-diffusion
  - absolute-beginner
---

- *Ultima modifica: sabato, 07/12/2024, alle 12:40.*

---

# 000 - Introduzione a Stable Diffusion

## Introduzione a Stable Diffusion

[Stable Diffusion](https://stability.ai/) è un [modello di diffusione latente](https://en.wikipedia.org/wiki/Latent_diffusion_model) per la generazione di immagini via intelligenza artificiale. Il sistema è in grado di produrre sia immagini fotorealistiche, che emulano la qualità di una fotografia professionale, sia composizioni artistiche paragonabili alle opere di grandi artisti.

L'aspetto più rilevante di questa tecnologia risiede nella sua natura *open source*. L'utente può eseguire il *software* sul proprio elaboratore oppure utilizzarlo attraverso servizi *online* a pagamento.

Il sistema, attraverso l'uso di interfacce dedicate (anche loro distribuite per lo più sotto licenze *open source*) è in grado di interpretare istruzione testuali fornite dell'utente (il *prompt*) e realizzare una immagine sulla base di queste. Ad esempio, questa è una immagine che ho ottenuto impostando come prompt lo splendido inizio del romanzo "Neuromante" di William Gibson:

> Il cielo sopra il porto aveva il colore della televisione sintonizzata su un canale morto.

![[Gibson.webp]]

## Metodologie di Utilizzo

### Generazione da Testo

La funzionalità primaria di Stable Diffusion consiste nella conversione di descrizioni testuali in immagini (*text-to-image*). Il sistema eccelle in diverse categorie stilistiche:

- Composizioni artistiche
- Fantasy
- Fotorealismo
- Paesaggistica
- Rappresentazioni zoologiche
- Stile *anime*

### Generazione da Immagine

La tecnologia supporta anche la trasformazione di immagini esistenti (*image-to-image*), permettendo la conversione di schizzi preliminari in opere elaborate o la modifica sostanziale di fotografie preesistenti.

### Editing Fotografico

Il sistema incorpora funzionalità avanzate di *editing*, tra cui:
- *Inpainting* per la rigenerazione selettiva di porzioni dell'immagine
- Strumenti di restauro facciale
- *Upscaling* per l'incremento della risoluzione

### Produzione Video

La piattaforma consente due approcci principali alla creazione video:
1. Generazione da *prompt* testuali
2. Stilizzazione di video preesistenti

## Linee Guida per la Formulazione dei Prompt

L'efficacia della generazione dipende criticamente dalla qualità del *prompt* fornito. Sono di provata efficacia tutti questi approcci:

1. Fornire descrizioni dettagliate e specifiche
2. Utilizzare termini chiave ad alto impatto
3. Specificare parametri stilistici
4. Includere riferimenti tecnici quando necessario

### Esempio di Prompt Base vs. Avanzato

Prompt base:
> una donna per strada

Prompt avanzato:
> giovane signora, occhi castani, capelli con riflessi, sorridente, abbigliamento business casual elegante, seduta all'esterno, strada cittadina tranquilla, illuminazione controluce

La differenza qualitativa tra i risultati risulterà sostanziale.

## Parametri Tecnici di Generazione

> [!warning]
> Attenzione: i parametri esposti qui sono assolutamente indicativi. Ogni LLM, ogni interfaccia e ogni procedura generativa esigono parametri specifici e spesso molto diversi tra loro.

L'ottimizzazione del processo generativo richiede la comprensione e la calibrazione di diversi parametri fondamentali:

### Parametri Essenziali

1. **Image Size**: 
   - Standard: 512×512 *pixels* | La modifica delle proporzioni influenza significativamente la composizione.

2. **Sampling Steps**: 
   - Minimo consigliato: 20 *steps* | Le "passate" per la generazione dell'immagine.

3. **CFG Scale**: 
   - *Default value*: 7 | L'incremento aumenta l'aderenza al *prompt*, ma può comportare decadimenti qualitativi di varia natura.

4. **Seed**: 
   - -1 per generazione casuale |  Valore cruciale per gestire la riproducibilità dell'immagine.

## Metodologie di Controllo Compositivo

### Tecniche Avanzate di Composizione

1. **img2img (Image-to-Image)**
   - Permette di utilizzare un'immagine di riferimento come base compositiva
   - Mantiene elementi strutturali conservando libertà creativa

2. **ControlNet**
   - Estrae informazioni specifiche (pose, contorni)
   - Particolarmente efficace per pose umane e strutture compositive

3. **Regional Prompting**
   - Consente di specificare prompt per aree distinte dell'immagine
   - Utile per composizioni complesse con elementi multipli

4. **Depth2img (Depth-to-Image)**
   - Analizza e replica la profondità dell'immagine di input
   - Mantiene la relazione tra primo piano e sfondo

## Modelli Personalizzati e Specializzati

### Tipologie di Modelli

1. **Modelli Base**:
  
  Esistono diverse generazioni di modelli Stable Diffusion; al momento in cui questo testo viene pubblicato, le famiglie più diffuse sono:

- Stable Diffusion v1.x e v2.x
- Stable Diffusion XL e 
- Flux.1 (schnell e dev)

2. **Modelli Personalizzati**:

Stable Diffusion permette di addestrare modelli, su caratteristiche specifiche. Si vedano, ad esempio, le migliaia di modelli disponibili su [Civitai](https://civitai.com/).

### Metodologie di Addestramento

> [!warning]
> Questi sono solo due tra i più diffusi sistemi di addestramento, ma non sono gli unici.

1. **Dreambooth**:
   - Ottimizzazione completa dei pesi del modello
   - Maggiore potenza di personalizzazione

2. **Embedding**:
   - Mantiene il modello originale intatto
   - Crea nuove associazioni keyword-soggetto

## Prompt Negativi

L'implementazione di prompt negativi costituisce uno strumento fondamentale per il controllo qualitativo dell'*output*. Questo metodo permette di specificare elementi indesiderati nella generazione, risultando particolarmente efficace nei modelli v1 e indispensabile per i modelli v2.

## Considerazioni Etiche e Legali

È doveroso sottolineare che l'utilizzo di questa tecnologia deve conformarsi a principi etici e normativi rigorosi. Si raccomanda particolare attenzione nell'evitare:
- Violazioni di copyright
- Generazione di contenuti inappropriati
- Uso improprio di identità personali