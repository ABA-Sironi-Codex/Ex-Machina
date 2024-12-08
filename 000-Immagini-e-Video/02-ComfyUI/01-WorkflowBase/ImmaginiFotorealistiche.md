---
title: Immagini Fotorealistiche in ComfyUI
date: 09/11/2023
tags:
  - comfyui
  - tecniche-base
---

- *Ultima modifica: sabato, 07/12/2024, alle 13:59.*

---

# Immagini Fotorealistiche in ComfyUI

> [!warning]
> Attenzione: questo tutorial è stato scritto il 9 novembre 2023. Da allora, l'interfaccia di ComfyUI è cambiata sensibilmente, i modelli si sono evoluti e alcune delle procedure descritte non sono più valide o hanno una trascurabile influenza sul risultato finale. 
> <p> </p>
> Rimane disponibile come testimonianza storica e per una sua validità generale, se seguito  con accortezza ed elasticità mentale.

### Intro

Questo flusso di lavoro può essere preso a modello da chiunque sia alle prime armi con la creazione di immagini attraverso IA Generative *Open Source*. Prima di accendere il fuoco, diamo un'occhiata agli ingredienti.

### Comfy UI

Una interfaccia a linea di comando molto semplice, ma anche molto potente. Ne esiste una versione _portable_ per Windows, molto bene ingegnerizzata. Puntate il navigatore [qui](https://github.com/comfyanonymous/ComfyUI), leggete bene tutta la documentazione, scaricate la versione giusta ed espandentela in una cartella del vostro HD.

Al termine di queste prime operazioni, nella vostra cartella avrete questo:

![[01.png]]

Il file *run_cpu.bat* riesce a lanciare Comfy UI su PC sprovvisti di GPU Nvidia, indirizzando tutti i calcoli alla CPU, ma i tempi di attesa sono ere geologiche ed è probabile che, col modello che useremo in questo esempio, si blocchi. Se non avete una GPU adatta, probabilmente è meglio che non andiate avanti.

All'interno della cartella *update* c'è il necessario per aggiornare eventuali componenti. Doppio clic su *update_comfyui.bat* e poi attenzione all'*output* di terminale. Il resto è intuitivo.

All'interno della cartella *ComfyUI* ci sono diverse cose (da non toccare!), ma a noi interessa solo la cartella *models*.

Il contenuto di *models* dovrebbe essere così:

![[02.png]]

Prendiamo nota che lì dentro ci sono le cartelle *checkpoints* ed *embeddings* e torniamo in rete.

### RealisticVision

RealisticVision è un modello in costante evoluzione che ha avuto un ottimo successo su Civitai. Al momento in cui scrivo la prima versione di questa guida è arrivato alla versione 5.1, ma la 6 è in dirittura d'arrivo ed è già stato scaricato più di 735.000 volte. La pagina dedicata su Civitai è qui:

[RealisticVision su Civitai](https://civitai.com/models/4201/realistic-vision-v51)

Attenzione! RV, generando immagini fotorealistiche, è in grado di creare anche contenuti [NSFW](https://en.wikipedia.org/wiki/Not_safe_for_work). 

Tra i download disponibili troverete modelli *full* e *pruned* di tipo *PickleTensor* e *SafeTensor*. La differenza tra uno e l'altro sarà oggetto di una guida a parte. Voi fate attenzione solo a scaricare modelli *SafeTensor*, scegliendo a seconda della disponibilità di spazio che avete sull'HD. L'opzione *full* sarebbe la più indicata e i risultati portati in questa pagina sono ottenuti con quella.

Scaricate il modello. Ora, tra i vostri download dovrebbe esserci un file che si chiama *realisticVisionV51_v51VAE.safetensors*, di circa 4.1 Gb. Mettetelo nella cartella *checkpoints* di ComfyUI e poi tornate dalle parte di Civitai.

### BadDream, UnrealisticDream, FastNegative Embedding

I *negative prompt* sono molto importanti, specie per evitare brutti risultati con le immagini fotorealistiche. Mani sbagliate, doppie teste e occhi strabici si possono controllare con i corretti *negative prompt*, ma arrivare a stilarne uno efficace può essere un lavoro davvero complesso. I tre file indicati sotto, facilitano molto il lavoro dei *negative prompt*. Possono lavorare insieme o separatamente, sia con *negative prompt* espliciti che non. Cominciamo con lo scaricarli.

 - [BadDream](https://civitai.com/models/72437?modelVersionId=77169) | Più indicato se si stanno creando figure umane. Può lavorare con *negative prompt* espliciti e non, in accoppiata con *FastNegative* o da solo.
 - [UnrealisticDream](https://civitai.com/models/72437?modelVersionId=77173) | Più indicato se si stanno creando paesaggi. Può lavorare con *negative prompt* espliciti e non, in accoppiata con *FastNegative* o da solo.
 - [FastNegative](https://civitai.com/models/71961/fast-negative-embedding) | Nessuna particolare indicazione. Può lavorare con *negative prompt* espliciti e non, in accoppiata coi due precedenti o da solo.

 Scaricateli tutti e tre (questa volta si tratta di poche centinaia di Kb) e metteteli nella cartella *embeddings*.

 ### Preparativi

Lanciate ComfyUI. Si apre il *network* di *default*. Il primo nodo *Load Checkpoin* mostra l'opzione *RealisticVision*.

![[03.png]]

### Positive prompt

 Lavoriamo con un *positive prompt* creato per generare immagini fotorealistiche in bianco e nero. Questo renderà il tutto un po' più veloce.

 ```Text
b&w photo of 60 y.o man in dark clothes, bald, sailor cap, face, half body, body, high detailed skin, skin pores, coastline, overcast weather, wind, waves, 8k uhd, dslr, soft lighting, high quality, film grain, Fujifilm XT3
```

Il *positive prompt* va scritto nel nodo *CLIP Test Encode* collegato alla porta *positive* del *KSampler*.

![[04.png]]

### KSampler e Latent Image

Questi i valori da impostare nei due rispettivi nodi.

 ```Text
Steps: 25,

Size: 640x960,

Seed: 2248258573,

Model: Realistic_Vision_V5.1,

Sampler: DPMpp SDE Karras,

CFG scale: 7
```

Se volete ottenere immagini diverse ad ogni generazione, lasciate il valore *control_after_generate* del nodo *KSamper* su *randomize*. Se invece volete studiare variazioni sulla stessa immagine, questo valore deve essere impostato su *fixed*.

![[05.png]]

### Negative prompt

 Stando alla [documentazione ufficiale] i *negative prompt* di default per RealisticVision sono due.

 ```Text
(deformed iris, deformed pupils, semi-realistic, cgi, 3d, render, sketch, cartoon, drawing, anime), text, cropped, out of frame, worst quality, low quality, jpeg artifacts, ugly, duplicate, morbid, mutilated, extra fingers, mutated hands, poorly drawn hands, poorly drawn face, mutation, deformed, blurry, dehydrated, bad anatomy, bad proportions, extra limbs, cloned face, disfigured, gross proportions, malformed limbs, missing arms, missing legs, extra arms, extra legs, fused fingers, too many fingers, long neck,
```

 ```Text
(deformed iris, deformed pupils, semi-realistic, cgi, 3d, render, sketch, cartoon, drawing, anime, mutated hands and fingers:1.4), (deformed, distorted, disfigured:1.3), poorly drawn, bad anatomy, wrong anatomy, extra limb, missing limb, floating limbs, disconnected limbs, mutation, mutated, ugly, disgusting, amputation,
```
In questa guida ho lavorato col primo. Logicamente, il *negative prompt* va scritto nel nodo *CLIP Test Encode* collegato alla porta *negative* del *KSampler*.

In questi due esempi, il risultato ottenuto con e senza *negative prompt* esplicito.

| **Senza NP** | **Con NP** |
| :----------: | :--------: | 
| ![[06a.png]] | ![[06b.png]] |

Aggiungiamo una chiamata all'embedding *negative prompt*.

```Text
(deformed iris, deformed pupils, semi-realistic, cgi, 3d, render, sketch, cartoon, drawing, anime), text, cropped, out of frame, worst quality, low quality, jpeg artifacts, ugly, duplicate, morbid, mutilated, extra fingers, mutated hands, poorly drawn hands, poorly drawn face, mutation, deformed, blurry, dehydrated, bad anatomy, bad proportions, extra limbs, cloned face, disfigured, gross proportions, malformed limbs, missing arms, missing legs, extra arms, extra legs, fused fingers, too many fingers, long neck, BadDream
```

In questi altri due esempi, il risultato ottenuto con *negative prompt* esplicito + *BadDream* e solo *BadDream*.

| **NP + BadDream** | **BadDream** |
| :----------: | :--------: | 
| ![[07a.png]] | ![[07b.png]] |

### Qualche variazione

Qualche variazione di soggetto, tutte ottenute con *negative prompt* esplicito + *BadDream*.

|     |     |     |
| :-: | :-: | :-: |
| ![[08.png]] | ![[09.png]] | ![[10.png]] |
| ![[11.png]] | ![[12.png]] | ![[13.png]] |

### E per i paesaggi?

Più o meno tutto lo stesso, con le dovute variaziani al *positive prompt*. Ecco qualche dato con cui partire.

 ```Text
RAW professional photo of autumn landscape, dramatic lighting, gloomy, cloudy weather
```

E per il *negative prompt* dovrebbe bastare questo.

 ```Text
text, cropped, out of frame, worst quality, low quality, jpeg artifacts, ugly, duplicate, mutation, deformed, blurry, dehydrated, bad anatomy, bad proportions, disfigured, gross proportions, BadDream, UnrealisticDream,
```

Per questo paesaggio ho lasciato invariato ogni parametro, a parte le dimensioni che ho settato su 1280x720 px.

![[14.png]]