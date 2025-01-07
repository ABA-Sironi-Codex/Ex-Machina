---
title: Le alternative
date: domenica, 08/12/2024
tags:
  - testi
  - chatbot
  - characters
---

- *Ultima modifica: domenica, 08/12/2024, alle 06:35.*

---

# Le alternative open source per installazioni locali

## Abstract

[BackyardAI](001-Introduzione-a-BackyardAI) [GPT4All](002-GPT4ALL) sono ottimi sistemi per creare sulle proprie macchine sistemi di intelligenza artificiale riservati, ma non sono gli unici. In questo articolo vediamo una panoramica delle principali alternative.

---

### 1. **Ollama**

![[ollama.png | Ollama gira direttamente da terminale]]

Ollama è uno strumento *open source* che consente l'esecuzione locale di modelli linguistici di grandi dimensioni, come Llama 3.2 e Mistral, direttamente sul proprio dispositivo. Offre un'interfaccia a riga di comando e supporta una immensa gamma di modelli. Viene spesso impiegato come "motore" per GUI.

- **Caratteristiche Principali**:
    - Esecuzione locale di modelli LLM.
    - Supporto per modelli come Llama 3.2 e Mistral.
    - Interfaccia a riga di comando.

- [Sito ufficiale](https://ollama.com/)

### 2. **Oobabooga**

![[Oobabooga_UI-2.png | Interfaccia principale di Oogabooga]]

Oobabooga è un'interfaccia web per l'esecuzione di LLM. Simile nell'approccio ad [Automatic1111](https://github.com/AUTOMATIC1111/stable-diffusion-webui) -  (sono entrambe basate su [Gradio](https://gradio.app/)) - quando viene lanciato crea "al volo" una interfaccia grafica in forma di sito *web* sul computer dell'utente che può quindi sfruttare il proprio *browser* per gestire il *software*.  Supporta vari modelli e offre funzionalità come *chat*, completamento di testo e generazione di codice. Anche Oobabooga viene spesso usato come "motore" per GUI più complesse, come ad esempio Silly Tavern.

- **Caratteristiche Principali**:
    - Interfaccia web per LLM.
    - Supporto per chat e completamento di testo.
    - Generazione di codice.

- [Sito ufficiale](https://github.com/oobabooga/text-generation-webui)

### 3. **Jan**

![[jan.png | Jan che genera la sequenza Fibonacci in Python]]

Jan è un'applicazione *open source*, disponibile per Linux, Macintosh e Windows, che consente l'esecuzione offline di modelli linguistici come Mistral o Llama direttamente sul dispositivo dell'utente, senza necessità di connessione internet. Offre un'interfaccia semplice e supporta l'importazione di modelli da fonti come Huggingface. Una buona alternativa a GPT4All, ma - almeno al momento in cui viene scritto questo articolo - leggermente meno efficace nel RAG.

- **Caratteristiche Principali**:
    - Esecuzione locale e offline di LLM.
    - Interfaccia user-friendly.

- [Sito ufficiale](https://jan.ai/)

### 4. **Msty**

![[msty-hero-image-light.webp | Msty può comparare le risposte di diversi LLM]]

Più o meno come GPT4All e Jan, Msty è un'applicazione desktop che consente di utilizzare modelli AI da Huggingface, Ollama e Open Router. Offre funzionalità come la comparazione in tempo reale delle risposte di diversi modelli e la creazione di conversazioni ramificate, rendendo il flusso di lavoro più efficiente.

- **Caratteristiche Principali**:
    - Integrazione con modelli da diverse fonti.
    - Comparazione in tempo reale delle risposte dei modelli.
    - Creazione di conversazioni ramificate.

- [Sito ufficiale](https://msty.app/)

### 5. **SillyTavern**

![[sillytavern.png | Interfaccia principale di SillyTavern]]

SillyTavern è una alternativa molto potente a [BackyardAI](001-Introduzione-a-BackyardAI) e, in generale, a tutti i sistemi di *chat* orientati al *roleplay* con personaggi personalizzati. È un *fork* di [TavernAI](https://github.com/TavernAI/TavernAI), offre un'interfaccia semplice per l'interazione con modelli AI, un ventaglio davvero stupefacente di funzioni ed è forte di una vasta comunità internazionale di appassionati.

- **Caratteristiche Principali**:
    - Interfaccia *user-friendly* per *chat* AI.
    - Supporto per la creazione di personaggi personalizzati.
    - Comunità estesa e molto attiva.

- [Sito ufficiale](https://github.com/SillyTavern/SillyTavern)

---

## Altro

Un elenco di altre ottime alternative.

- [Alpaca](https://github.com/Jeffser/Alpaca) (solo Linux)
- [Anything-LLM](https://github.com/Mintplex-Labs/anything-llm)
- [Farfalle](https://github.com/rashadphz/farfalle)
- [KoboldCPP](https://github.com/LostRuins/koboldcpp)
- [LLM Studio](https://lmstudio.ai/)
- [LocalAI](https://github.com/mudler/LocalAI)
- [Google Notebook LM](https://notebooklm.google.com)
- [OpenWebUI](https://github.com/open-webui/open-webui)
- [Pinokio](https://pinokio.computer/)
- [PrivateGPT](https://github.com/zylon-ai/private-gpt)
- [Secret Llama](https://github.com/abi/secret-llama)