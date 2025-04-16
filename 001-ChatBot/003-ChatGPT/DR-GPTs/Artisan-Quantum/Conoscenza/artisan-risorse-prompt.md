# Guida ai Prompt Visivi per AI – Stable Diffusion, FLUX, DALL·E, Sora

## 1. Introduzione
Questa guida raccoglie principi, tecniche e strategie per scrivere prompt ottimizzati per la generazione di immagini e video tramite modelli AI come Stable Diffusion (SD), FLUX, DALL·E e Sora. È pensata per artisti digitali, designer computazionali e creatori visivi che vogliono ottenere risultati coerenti, estetici e controllabili.

---

## 2. Struttura base di un prompt visivo

Un prompt efficace include:
- **Soggetto**: cosa viene rappresentato (es. "a futuristic city")
- **Contesto o azione**: scenario e interazione (es. "during a rainy night")
- **Stile**: riferimento artistico, tecnico o estetico (es. "in the style of Moebius" / "isometric vector art")
- **Tecnica visiva**: tipo di rendering, luci, materiali (es. "octane render, global illumination")
- **Controlli opzionali**: aspect ratio, negativi, camera angle, dettagli di luce, composizione

Esempio:
```
a gothic cathedral in the forest at twilight, volumetric lighting, ultra wide shot, intricate details, Unreal Engine style, cinematic
```

---

## 3. Prompt per Stable Diffusion (SD / SDXL)

### 3.1 Struttura consigliata
```
<subject>, <environment>, <lighting>, <style>, <camera>, <rendering tags>, <artist ref>, <resolution/detail>
```

### 3.2 Elementi comuni
- **Soggetti**: portrait of..., landscape of..., macro shot of...
- **Ambienti**: underwater, outer space, neon-lit alley
- **Luce**: volumetric light, backlight, golden hour, studio lighting
- **Tecnica**: octane render, unreal engine, photorealistic, anime, painterly
- **Camera**: close-up, top-down, over-the-shoulder, wide shot
- **Negativi (Negative Prompt)**: blurry, distorted, extra fingers, bad anatomy, watermark, low-res

### 3.3 Tools correlati
- ComfyUI, Automatic1111, InvokeAI, Fooocus
- ControlNet: pose, depth, lineart, canny
- LoRA, embeddings: per stile e personaggi custom

---

## 4. Prompt per FLUX

FLUX utilizza un linguaggio simile a SD ma è orientato alla narrazione visiva, fluidità e movimento implicito. Predilige descrizioni che evocano atmosfera, trasformazione e temporalità.

### 4.1 Linee guida
- Inserire emozioni, cambiamenti, contrasti
- Descrizioni poetiche o narrative
- Funziona bene con prompt complessi multilivello

### 4.2 Esempio:
```
A girl made of shifting stardust walks through an endless desert of glass dunes, soft winds disturb her form, dreamlike light, ambient haze, surreal cinematic mood
```

---

## 5. Prompt per DALL·E (3)

DALL·E comprende linguaggio naturale in modo molto accurato. È efficace con prompt brevi ma ben articolati.

### 5.1 Suggerimenti
- Specifica **cosa**, **dove**, **quando**, **come**
- Non serve usare keyword tecniche (es. “octane render”), ma è utile indicare stile e medium
- Può seguire istruzioni multi-turn (es. "generate 4 variations")

### 5.2 Esempio:
```
An oil painting of a raven perched on a glowing lantern in a snow-covered forest at dawn, expressive brushstrokes, high contrast, inspired by 19th-century romanticism
```

---

## 6. Prompt per Sora

Sora genera video brevi partendo da una descrizione singola. I prompt devono suggerire chiaramente:
- **soggetto**, **movimento**, **ambiente**, **luce**, **atmosfera**, **tipo di ripresa** (cinematica, documentaristica, onirica)

### 6.1 Caratteristiche
- Comprende bene linguaggio cinematografico
- Valuta il movimento implicito: uso di verbi
- È sensibile al tono (poetico, tecnico, descrittivo)

### 6.2 Esempio:
```
A drone shot of a massive waterfall cascading into a misty jungle valley, sunlight piercing through the canopy, birds flying across the frame, cinematic depth of field
```

---

## 7. Tecniche avanzate

### 7.1 Prompt layering
Unisci più blocchi con AND/commas. Può essere utile per FLUX e SDXL.

### 7.2 Prompt evolutivi
- Crea sequenze temporali (Sora) o serie coerenti (DALL·E)
- Cambia solo un parametro per volta: luce, tempo, soggetto

### 7.3 Mix di stili
```
A street scene in Tokyo, mix of cyberpunk and ukiyo-e, top-down, ultra-saturated neon palette, fog in the background
```

---

## 8. Link di riferimento
- Prompt examples e tools: https://promptomania.com/
- Stable Diffusion Art: https://stable-diffusion-art.com/
- Lexica Art (prompt + immagini): https://lexica.art/
- PromptHero (galleria + generatore): https://prompthero.com/
- DALL·E official guide: https://platform.openai.com/docs/guides/images
- Awesome Prompts (GitHub): https://github.com/f/awesome-chatgpt-prompts
- Visual Prompt Book (PDF): https://openart.ai/promptbook
- Prompt Engineering Patterns: https://learnprompting.org/

Fine della guida.