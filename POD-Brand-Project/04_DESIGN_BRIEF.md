# 🎨 DESIGN BRIEF & WORKFLOW

## Specifiche file stampa (obbligatorie)

| Parametro | Valore |
|---|---|
| Risoluzione | **300 DPI** |
| Dimensione tela | min. 4500×5400 px (area stampa A3+) |
| Formato | PNG con trasparenza |
| Profilo colore | **sRGB IEC61966-2.1** (NON CMYK) |
| Fondo | Trasparente |
| Tessuto scuro | Aggiungere underbase bianca sotto il design |

## Posizionamenti che vendono

| Posizione | Quando usarla |
|---|---|
| Chest print (sx o centro) | Default versatile, minimal |
| Full back print | Statement streetwear, alta percezione valore |
| Oversized front | Y2K, bold |
| Sleeve print | Dettaglio premium, differenziante |

## Stili 2026 prioritari (dalla ricerca)

1. Vintage / Distressed
2. Bold typography
3. Minimalista / micro-logo
4. Y2K / cyber
5. Hand-drawn illustration
6. Gothic / dark aesthetic

## Workflow ComfyUI per grafiche stampabili

```
1. GENERA soggetto → Flux.1 Dev (testi leggibili) o SDXL+Lightning (velocità)
2. UPSCALE 4× → Real-ESRGAN / 4x-UltraSharp
3. RIMUOVI sfondo → nodo REMBG
4. ESPORTA → PNG 300 DPI, sRGB, trasparente
5. COMPOSITING finale → Photoshop/Affinity (font, layout, ritocco)
   ⚠️ Aggiungi sempre ≥20-30% di intervento umano (copyright)
```

**Modelli consigliati per nicchia:**
- Streetwear minimal/typography → Flux.1 Dev
- Anime/illustration → Pony Diffusion / SDXL anime
- Vintage/distressed → SDXL + LoRA grunge/vintage

## Mockup lifestyle (vantaggio competitivo)

Workflow ComfyUI + ControlNet:
```
1. Genera/scegli persona (OpenPose ControlNet)
2. Inpaint il design sul capo indossato
3. Match luce e prospettiva
4. Output 1080×1920 per TikTok/IG, 2000×2000 per Etsy
```

In alternativa rapida: Higgsfield image generation, Placeit, Printful Mockup Generator.

## Errori da evitare

- ⛔ Font sotto 14pt (illeggibili in DTG)
- ⛔ Dettagli fini su tessuto scuro senza underbase
- ⛔ Colori CMYK (shift cromatico in stampa)
- ⛔ Troppo testo (streetwear = impatto visivo)
- ⛔ Replica di trend già saturi

## Checklist pre-caricamento prodotto

- [ ] PNG 300 DPI sRGB trasparente
- [ ] Design centrato sull'area stampa del template
- [ ] Test su mockup chiaro E scuro
- [ ] Nome file descrittivo (SEO interno)
- [ ] Intervento umano sufficiente (copyright)
