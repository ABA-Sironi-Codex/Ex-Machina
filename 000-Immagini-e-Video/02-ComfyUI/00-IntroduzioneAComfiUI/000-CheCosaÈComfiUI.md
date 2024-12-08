---
title: Che cos'è ComfyUI
date: sabato, 07/12/2024
tags:
  - comfyui
  - absolute-beginner
---

- *Ultima modifica: sabato, 07/12/2024, alle 20:04.*

---

# Che cos'è ComfyUI

## Intro

[ComfyUI](https://github.com/comfyanonymous/ComfyUI) è un sistema di gestione di modelli Stable Diffusion che permette di creare  "flussi" di generazione di immagini o video, chiamati "*workflow*", utilizzando "blocchi", chiamati "nodi", che svolgono funzioni diverse.

In altre parole, è un sistema per la generazione di immagini e video che offre una interfaccia simile a quella di altri framework di programmazione a nodi come, solo per fare qualche esempio:

- [Cables](https://cables.gl/)
- [Nodebox](https://www.nodebox.net/)
- [Touchdesigner](https://derivative.ca/)

I nodi più comuni sono:

- Caricamento di un modello Stable Diffusion
- Inserimento di un prompt
- Gestione del processo di *sampling* (ne parleremo tra poco)
- Visualizzazione delle immagini generate.

![[WorkflowBase.png | Workflow di default in ComfyUI]]

## Pro e contro

### Pro

- Leggerezza
- Flessibilità
- Feedback: il flusso di dati è visibile. Questo semplifica l'identificazione di eventuali *bug* nei *workflow*.
- Condivisibilità: i workflow sono file json di pochi Kb, facilmente trasferibili.

### Contro

- Curva di apprendimento ripida e interfaccia ostica: è necessario conoscere bene Stable Diffusion per creare i propri *workflow* e l'interfaccia in generale non è adatta a chi va di fretta o non ha voglia di passare pomeriggi a leggere documentazione.
- Interfaccia incoerente: ogni *workflow* può posizionare i nodi in modo diverso. 

## Utilizzo

ComfyUI può essere utilizzato scaricando ed installando lo *script* (e tutti i modelli necessari) sul proprio computer oppure attraverso servizi *online*.

Per utilizzare ComfyUI in locale, sono disponibili versioni per tutti i sistemi operativi e dettagliate istruzioni d'uso sul [repository ufficiale](https://github.com/comfyanonymous/ComfyUI).

Per i servizi online, c'è l'[imbarazzo della scelta](002%20-%20Generatori%20On%20Line).

