---
title: Il primo workflow
date: sabato, 07/12/2024
tags:
  - comfyui
  - absolute-beginner
---

- *Ultima modifica: sabato, 07/12/2024, alle 20:04.*

---

# Il primo workflow

![[WorkflowBase.png | Il workflow di default]]

Appena lanciato, subito dopo l'installazione, ComfyUI dovrebbe aprirsi sul *workflow* di *default* (*image generation*), che poi è sempre possibile richiamare, insieme ad alcuni altri, molto basici, con un clic sul pulsante *workflows* della barra a sinistra.

![[workflowdisponibili.png | I workflow disponibili di default]]

I nodi come *Load Checkpoint*, *Clip Text Encoder*, sono metafore grafiche per istruzioni e funzioni di programmazione, collegate tra loro da cavi che mostrano il flusso dei dati nel *workflow*. 

Ogni nodo ha:

- Porte di ingresso (a sx)
- Porte di uscita (a dx)
- Istruzioni e parametri (alcuni nodi non ne hanno)

![[nodoesempio.webp | Il nodo "KSampler" ha 4 ingressi e 1 uscita]]

![[nodocheckpoint.webp | Il nodo "Checkpoint" è quasi sempre il primo in un *workflow* e non ha ingressi]]

I modelli sono scaricabili da diversi siti: i più famosi sono [Civitai](https://civitai.com/) e [Huggingface](https://huggingface.co/). Ogni modello può pesare da 2 più di 10 Gb e vanno posizionati nella cartella: 

Comfyui > models > checkpoints folder.

Una volta scaricati, potranno essere selezionati nel nodo *Checkpoint*. Un ottimo modello con cui iniziare potrebbe essere [Dreamshaper](https://civitai.com/models/4384/dreamshaper).

I due nodi *Clip Text Encode* raccolgono il *prompt* positivo (quello che si vuole ottenere) e negativo (quello che non si vuole ottenere) dell'utente. I prompt non sono soggetti a particolari sintassi (per lo meno, non in questa fase di studio), ma sono sensibili ai "pesi" con cui è possibile controllare il "peso" di determinate parole chiave, all'interno del *prompt*. Ad esempio, scrivendo (rosso:1.2), il termine "rosso" avrà particolare importanza, mentre scrivendo (verde:0.8), il termine "verde", pur restando all'interno del *prompt*, assumerà importanza minore rispetto agli altri.

![[EmptyLatent.png | Questo nodo governa le dimensioni dell'immagine finale. Il valore "Batch size" regola il numero di immagini da produrre per ogni clic su "Queue" (vedi più sotto)]]

![[vae.png | Il nodo "VAE Decode" non ha parametri e serve a "spostare" l'immagine dallo [spazio latente](https://samanemami.medium.com/a-comprehensive-guide-to-latent-space-9ae7f72bdb2f) alla dimensione dei pixel]]

![[queue.png | La generazione delle immagini partirà al clic sul pulsante "Queue"]]

# Esercizi

Non è una buona idea affrontare workflow più complessi, prima di avere imparato a:

- Modificate i propri *prompt* positivi e negativi
- Cambiare i formati dell'immagine generata
- Generare più immagini con un solo workflow
- Utilizzare diversi *checkpoint*.

La rete è piena di tutorial e guide in merito. Questo [*tutorial* di Olivio Sarikas](https://youtu.be/LNOlk8oz1nY?feature=shared) è ottimo per imparare a conoscere i principi base dell'interfaccia di ComfyUI.

<iframe width="560" height="315" src="https://www.youtube-nocookie.com/embed/LNOlk8oz1nY?si=DttlvbsBYSCwSS3V" title="YouTube video player" frameborder="0" allow="accelerometer; autoplay; clipboard-write; encrypted-media; gyroscope; picture-in-picture; web-share" referrerpolicy="strict-origin-when-cross-origin" allowfullscreen></iframe>