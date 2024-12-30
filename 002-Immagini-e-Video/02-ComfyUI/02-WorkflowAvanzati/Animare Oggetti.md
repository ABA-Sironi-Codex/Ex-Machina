---
title: Animare oggetti
date: sabato, 07/12/2024
tags:
  - comfyui
  - tecniche-avanzate
  - video
---

- *Ultima modifica: sabato, 07/12/2024, alle 13:59.*

---

# Animare oggetti in ComfyUI

## Intro

I *workflow* avanzati non hanno particolari spiegazioni e sono commentati direttamente all'interno del file.

## Obiettivo

Creare un breve video di oggetti inanimati sulla traccia di un movimento pre-esistente. Ad esempio: partendo dal movimento di una ballerina e imponendolo ad un piatto di spaghetti, è possibile ottenere un video di spaghetti danzanti.

## Modelli

- [AnimateDiff LCM Motion](https://civitai.com/models/326698/animatediff-lcm-motion-model) in ComfyUI > models > animatediff_models.
- [Dreamshaper 8](https://huggingface.co/Lykon/dreamshaper-8-lcm/blob/main/DreamShaper8_LCM.safetensors) in ComfyUI > models > checkpoints.
- [QR Monster ControlNet](https://huggingface.co/monster-labs/control_v1p_sd15_qrcode_monster/blob/main/control_v1p_sd15_qrcode_monster.safetensors) in ComfyUI > models > controlnet .
- [SD 1.5 CLIP vision](https://huggingface.co/h94/IP-Adapter/resolve/main/models/image_encoder/model.safetensors)in ComfyUI > models > clip_vision [da rinominare in `CLIP-ViT-H-14-laion2B-s32B-b79K.safetensors`.
- [SD 1.5 IP adapter Plus](https://huggingface.co/h94/IP-Adapter/blob/main/models/ip-adapter-plus_sd15.safetensors) in ComfyUI > models > ipadapter.
- [Soft Edge ControlNet](https://huggingface.co/lllyasviel/ControlNet-v1-1/blob/main/control_v11p_sd15_softedge.pth) in ComfyUI > models > controlnet.

## Materiali di partenza

![[AnimaOggetti.7z]]

## Note

L'oggetto è controllato dal *prompt* e dall'*IP-adapter*. Per cambiare oggetto, bisogna cambiare entrambi. Se necessario, bisogna cambiare anche l'*object template image* scegliendo una tinta piatta vicina alla dominante del soggetto. Anche lo sfondo (background image*) dovrà essere adattato di conseguenza.