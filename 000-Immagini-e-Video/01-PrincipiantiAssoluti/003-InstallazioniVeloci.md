---
title: titolo post
date: martedì, 10/12/2024
tags:
  - stable-diffusion
  - absolute-beginner
---
- *Ultima modifica: martedì, 10/12/2024, alle 23:18.*

---

# Installazioni veloci (solo GPU nVidia)

[Automatic1111 Web UI](https://github.com/AUTOMATIC1111/stable-diffusion-webui) - spesso abbreviata in Automatic1111 o A1111 - è una delle più diffuse interfacce di controllo per [Stable Diffusion](https://stability.ai/stable-diffusion). Oltre alle consuete operazioni di generazione _Text-2-Image_, la struttura modulare di A1111 permette una infinità di operazioni accessorie come, solo per fare alcuni esempi, la generazione di matrici di miniature per confrontare la differenza ottenuta con la variazione di questo o quel parametro, la creazione di video e di musica, etc.

Il _repository_ ufficiale contiene istruzioni molto dettagliate sugli *step* di installazione sotto qualsiasi genere di sistema operativo. Queste procedure variano (o potrebbero variare) ad ogni nuovo rilascio e si consiglia di verificarle direttamente alla fonte.

- [A1111 Installation Instructions](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki)

Quelle che seguono sono le istruzioni per installazioni rapide su computer i cui requisiti si sia certi che soddisfano le richieste del sistema.

## Installazione su Ms Windows con GPU Nvidia

1. Scaricate il file _sd.webui.zip_ da [qui](https://github.com/AUTOMATIC1111/stable-diffusion-webui/releases/tag/v1.0.0-pre) (probabilmente andrà aggiornato, ma lo faremo al punto 3).
2. Estrarre il file zip nella posizione desiderata.
3. Doppio clic su _update.bat_ per aggiornare tutto all'ultima versione, attendere il completamento dell'operazione e chiudere la finestra.
4. Doppio clic su _run.bat_ per avviare l'interfaccia web; durante il primo avvio verrà scaricata una grande quantità di file. Dopo che tutto è stato scaricato e installato correttamente, dovrebbe apparire il messaggio _Esecuzione su URL locale: http://127.0.0.1:7860_; aprendo il link si accede all'interfaccia di controllo ed è possibile iniziare a generare immagini su _prompt_ di testo.

### Configurazioni extra via COMMANDLINE_ARGS

È possibile configurare alcune opzioni modificando lo _script_ di lancio che si trova in _sd.webui\webui\webui-user.bat_, aggiungendo gli argomenti desiderati dopo _COMMANDLINE_ARGS=_. Ad esempio:

`set COMMANDLINE_ARGS=--autolaunch --update-check`

configura l'interfaccia in modo che venga avviata automaticamente la pagina del browser al termine del caricamento e che venga verificata la presenza di aggiornamenti all'avvio.

### Risoluzione dei problemi

La configurazione predefinita dell'interfaccia web dovrebbe funzionare sulla maggior parte delle moderne GPU, ma in alcuni casi potrebbero essere necessari alcuni argomenti aggiuntivi.

- Per le GPU con una quantità inferiore di VRAM, potrebbero essere necessari _--medvram_ o _--lowvram_; queste ottimizzazioni riducono i requisiti di VRAM, sacrificando proporzionalmente le prestazioni. Se la VRAM non è sufficiente, l'interfaccia web potrebbe rifiutarsi di avviarsi o non generare immagini a causa di un errore di esaurimento della memoria. La quantità di VRAM richiesta dipende in larga misura dalla risoluzione dell'immagine desiderata; per maggiori dettagli, consultate la [pagina di Troubleshooting ufficiale](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Troubleshooting). Anche l'estensione [Tiled VAE](https://github.com/pkuliyi2015/multidiffusion-upscaler-for-automatic1111) può aiutare a ridurre i requisiti di VRAM.

- Se le immagini generate sono nere o verdi, provare ad aggiungere _--precision full_ e _--no-half_ ai parametri di lancio.

- Alcune combinazioni di modello/VAE sono inclini all'erroe _NansException: A tensor with all NaNs was produced in VAE_ che finisce col dar luogo a un'immagine nera; l'uso dell'opzione _--no-half-vae_ può contribuire a mitigare il problema.

- Per ulteriori ottimizzazioni consultate le pagine ufficiali [Optimization](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Optimizations) e [Command Line Arguments and Setting](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Command-Line-Arguments-and-Settings).

## Installazione su Ms Windows con GPU AMD

Per il momento, A1111 non supporta ufficialmente AMD. È comunque possibile riuscire a installarne una versione sperimentale attraverso il _fork _creato da Lshqqytiger. Il repository offre anche una guida molto dettagliata.

- [Lshqqytiger Stable-Diffusion-WebUI-DirectMl](https://github.com/lshqqytiger/stable-diffusion-webui-directml)

## Installazione su Apple Macintosh

L'installazione sotto Mac è possibile, ma richiede molti passaggi intermedi. Fate riferimento alla guida ufficiale:

- [Installation on Apple Silicon](https://github.com/AUTOMATIC1111/stable-diffusion-webui/wiki/Installation-on-Apple-Silicon)