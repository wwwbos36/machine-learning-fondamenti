# PROJECT BRIEF — Replica del canale YouTube "Revenge Orchid"

> **Come usare questo file:** è un briefing di handoff per una chat Claude Code.
> Contiene (1) cosa abbiamo scoperto analizzando il canale target, (2) la strategia,
> (3) lo stack di tool da usare, (4) le istruzioni operative passo-passo.
> Leggi tutto prima di agire. Le sezioni "AZIONE" sono i compiti concreti da eseguire.

---

## 0. CONTESTO IN UNA FRASE

Vogliamo creare un canale YouTube **faceless** in lingua **inglese (US)** nella nicchia
**"AI-narrated family-revenge storytime"** (storie di vendetta familiare narrate, video lunghi),
replicando la *struttura* di un canale di successo chiamato **Revenge Orchid**, ma con
**brand, estetica e storie originali nostre** (per evitare copyright / reuse / demonetizzazione).

**Vincolo tecnico chiave:** per la generazione di immagini, video e voce usiamo
**HIGGSFIELD** (via MCP). NON usiamo ComfyUI. NON usiamo Midjourney.

---

## 1. COSA ABBIAMO SCOPERTO — Analisi del canale target (DATI REALI VERIFICATI)

Canale analizzato: **Revenge Orchid** — `https://www.youtube.com/@RevengeOrchidUS/videos`

| Dato | Valore reale |
|---|---|
| Account creato | 15 Dic 2012 (**account vecchio riattivato**, non nuovo) |
| Iscritti | 7.090 |
| Views totali | 900.242 |
| N° video | 22 (tutti pubblicati nell'ultimo ~mese) |
| Frequenza | ~5 video/settimana (pipeline AI ad alto volume) |
| Paese / Lingua | USA / Inglese US |
| Crescita | Esponenziale, trainata dall'algoritmo (browse/suggested), NON dagli iscritti |
| Rapporto views/iscritti | ~6x (media ~43K views per video con soli 7K iscritti) |

**Video-trigger virale:** *"Parents Planned To Turn My Lake House Into A Free 3-Day Getaway
For 20 Relatives—Without Asking Me…"* → 99K views, 36:20, 4.1K like. È il video che ha
agganciato l'algoritmo.

**Video meno performante (escluso annuncio):** "My Brother Prank-Called My Boss And Got Me
Fired" → 28K views, 45:54. Motivi: tra i primi pubblicati + il più lungo + hook meno carico
emotivamente.

### Caratteristiche del format (verificate)
- **Durata:** tutti i video reali stanno tra 32 e 46 min, concentrati su **35–38 min**
  (scelta per massimizzare i mid-roll ad).
- **Struttura narrativa:** hook → setup personaggio/torto → escalation conflitto familiare →
  umiliazione pubblica → twist silenzioso della protagonista (prove/documenti/telefonata/
  polizia/giudice/boss) → ribaltamento e giustizia → chiusura morale. Sempre **storytime in
  prima persona femminile**.
- **Visual:** cornice "scrapbook" pastello con orchidea + logo + ritratto AI del personaggio
  con nome sovrimpresso (es. "Emily") + avatar narratrice in basso a sinistra + **didascalie
  animate grandi full-screen** sincronizzate alla voce. Immagini AI statiche, NON stock, NON
  screenshot reali di Reddit.
- **YouTube applica il badge "AI"** ai loro video (disclosure contenuto sintetico) → confermato
  uso di media generati con AI.
- **Audio:** voiceover femminile (quasi certamente TTS tipo ElevenLabs), musica soft in
  sottofondo, voce in primo piano. ⚠️ Da verificare ascoltando.
- **Thumbnail:** blocco di testo multicolore (giallo/rosa/verde/bianco) che riassume la storia
  con keyword evidenziate + ritratto donna AI a destra + bordo neon + font bold maiuscolo
  condensed. Curiosity gap 9/10. Coerenza visiva 10/10.
- **SEO:** titolo in prima persona con torto + cliffhanger troncato con "…" o "Then…";
  descrizione con keyword stuffing ("reddit story, revenge stories, family stories") + nome
  personaggio inventato. Nessun capitolo.

### ⚠️ Rischi identificati
- Keyword stuffing + format ripetitivo + media AI = esposizione alla policy YouTube su
  **"contenuti inautentici/ripetitivi"** (inasprita 2025-2026). Il badge AI è già applicato ai
  competitor. → La nostra difesa: storie originali, brand visivo diverso, varietà tra episodi.

---

## 2. NICCHIA E COMPETITOR

- **Nicchia specifica:** AI-narrated **family-revenge** storytime long-form (protagonista donna,
  torto familiare, giustizia morale finale con prove). NON "revenge" generico.
- **Saturazione:** ALTA — è una "gold rush". Cloni diretti rilevati: Revenge Betrayal, Karma's
  Cycle, Revenge Room, Payback Ties, Revenge Chapters, Revenge Regret, Whispers of the Heart,
  GoldenHeart Lane, Revenge Mode.
- **CPM stimato ⚠️:** $4–$12 (USA, adulti, long-form con mid-roll). Da verificare con dati propri.
- **Pubblico ⚠️:** prevalentemente donne 35-65+, USA, fruizione passiva (TV/mobile in sottofondo).
- **Leva psicologica:** indignazione morale + revenge fantasy + bisogno di chiusura
  ("justice served"). Il long-form funziona come "podcast da ascoltare" → massimizza watch-time.
- **Lingua:** INGLESE (CPM e bacino enormemente superiori all'italiano).

### 🎯 GAP DI MERCATO (la nostra opportunità)
Tutti i competitor usano **un ritratto AI statico**. Nessuno cura varietà editoriale o visual
in movimento. La nostra leva: **scene animate per-beat con Higgsfield** (`generate_video`),
personaggio coerente tra le scene, voce espressiva. Questo ci differenzia E riduce il rischio
"contenuto inautentico".

---

## 3. LE FORMULE REPLICABILI

### 🎯 HOOK (primi 10s)
`[Evento scioccante] + [chi me l'ha fatto: familiare] + [umiliazione/torto] → [promessa di ribaltamento]`
Es: *"After a night shift, I came home to find my parents had given away my lake house —
without asking me. They had no idea what I was about to do."*

### 🎯 TITOLO
`[Antefatto 1ª persona, torto familiare specifico] [verbo forte] + [cliffhanger troncato "…"/"Then…"]`

10 titoli originali pronti all'uso:
1. My Sister Read My Diary At Her Wedding Toast—Then I Stood Up With A Folder…
2. My Dad Sold My Car To Fund My Brother's Startup. He Forgot Whose Name Was On The Loan…
3. My Mom Uninvited Me From Christmas For "Embarrassing The Family." Then My Lawyer Called…
4. My In-Laws Locked Me Out During The Storm. The Next Morning, Three Officers Knocked…
5. My Brother Demanded I Pay For His Honeymoon. I Smiled And Sent One Email…
6. My Stepmother Threw Out My Late Mom's Letters. She Didn't Know I Recorded Everything…
7. They Sat Me At The Kids' Table At 34. By Dessert, Nobody Was Laughing…
8. My Sister Claimed My Promotion Was "Just Luck." Then HR Called Her In…
9. My Family Skipped My Graduation For My Cousin's Party. Five Years Later, I Returned The Favor…
10. My Husband's Family Called Me "Just A Nurse." Then The Surgeon Walked In And Said My Name…

### 🎯 SCRIPT TEMPLATE (struttura, ~350 parole per il pilota / scalabile a 35-40 min)
1. Apertura/hook: nome + situazione + torto improvviso.
2. Setup: la protagonista è quella che "tiene insieme tutto", data per scontata.
3. Innesco: il torto pubblico/familiare specifico.
4. Escalation: la famiglia rincara; lei resta calma ("I didn't argue. I didn't cry.").
5. Pivot silenzioso: lei ha una prova / un documento / un alleato (boss, giudice, nonno, polizia).
6. Reveal: il ribaltamento al momento giusto.
7. Risoluzione + morale: confine posto, dignità riconquistata.
8. Mini-CTA soft: invito a commentare + iscriviti.

### 🎯 ALTRE FORMULE
- **Durata:** sweet spot 35–40 min (long-form). Per il PILOTA: 60–90 secondi.
- **Ritmo ⚠️:** caption full-screen ogni ~2-4s; cambio scena/ritratto ogni 20-40s.
- **Audio:** 1 voce femminile narrante calda in primo piano + bed musicale a -18/-20 dB +
  leggeri SFX sui momenti di tensione. Parlato cadenzato medio-lento.
- **Thumbnail:** sfondo chiaro/neon + blocco testo-riassunto multicolore con keyword evidenziate
  + ritratto donna AI a destra + bordo neon + font bold maiuscolo. NB: usare palette NOSTRA,
  non clonare il pastello-orchidea.

---

## 4. TOOL STACK (HIGGSFIELD-FIRST)

| Funzione | Tool | Note |
|---|---|---|
| Ideazione storie | LLM (Claude/GPT) | poi **riscrittura editoriale umana** (requisito anti-reuse) |
| Ritratti personaggio coerenti | **Higgsfield `generate_image`** + reference/character elements | consistenza personaggio tra scene |
| **Scene animate per-beat** | **Higgsfield `generate_video`** / `motion_control` | **questo è il nostro differenziatore** |
| Voiceover | **Higgsfield `generate_audio`** + `list_voices` | alternativa: ElevenLabs se serve voce specifica |
| Reframe Shorts (9:16) | **Higgsfield `reframe`** | per clip verticali |
| Test pre-pubblicazione | **Higgsfield `virality_predictor`** | hook strength / retention risk |
| Montaggio + caption animate | CapCut (free) o Premiere/After Effects | template riutilizzabile |
| Thumbnail | Canva o Photoshop | palette nostra |
| Ricerca temi (solo ispirazione) | Reddit (r/AmItheAsshole, r/EntitledParents, r/JUSTNOFAMILY, r/pettyrevenge) | NON copiare: storia 100% originale |

**Note operative Higgsfield (MCP):**
- Se non sai quale modello usare, chiama `models_explore(action:'recommend')` prima di generare.
- Per media locali dell'utente usa `media_upload_widget`; per URL web usa `media_import_url`
  e passa il `media_id` (mai URL grezzi nei params).
- Per migliorare un asset esistente usa i tool dedicati (`upscale_image`, `upscale_video`,
  `outpaint_image`, `remove_background`) invece di rigenerare.

**Stima costi mensili ⚠️:** ~$25–$95/mese (Higgsfield + LLM + CapCut/Canva eventuali Pro).

---

## 5. PIANO OPERATIVO

### >>> AZIONE IMMEDIATA — PILOTA DA 60-90 SECONDI (FARE PER PRIMA COSA)
**Obiettivo:** validare che il workflow Higgsfield produca un personaggio COERENTE tra le scene.
È il punto critico: se il volto del personaggio cambia ad ogni scena, il format non funziona.
Testarlo su 90 secondi, NON su un video da 36 minuti.

Sequenza:
1. Scegliere 1 titolo dalla lista (consigliato uno stile "Lake House", il pattern che ha bucato).
2. Scrivere ~150 parole di script (hook + setup + un mini-reveal).
3. Higgsfield: generare il ritratto del personaggio → bloccarlo come reference →
   generare 4-5 scene video brevi che RIUSANO lo stesso personaggio → generare il voiceover.
4. CapCut: montare, aggiungere caption full-screen + bed musicale.
5. Passare il risultato in `virality_predictor` e leggere hook strength / retention risk.
6. Decidere: se la coerenza personaggio regge → scalare a long-form. Altrimenti iterare i prompt.

### Settimana 1 — Setup
- Brand ORIGINALE: nome, logo, palette propria (NON clonare il pastello-orchidea).
- Stack minimo operativo: LLM + Higgsfield + CapCut + Canva.
- Lista di 20 argomenti (usare la formula titolo).
- Scegliere i primi 3 (hook più forte, twist con prova chiara, emozione più universale).
- NB: account/password/pagamenti li gestisce l'utente. Claude non crea account.

### Settimana 2 — Video 1 (long-form)
- Script completo dal template (riscritto a mano).
- Voiceover Higgsfield → ritratto + scene video → montaggio 35-38 min → thumbnail (gap 8+/10).

### Settimane 3-4 — Pubblicazione e test
- Titolo + metadati SEO (senza keyword-stuffing eccessivo).
- Pubblicazione fascia serale US (⚠️ stima 16-20 ET).
- 3-5 hashtag tematici. Primo commento "ancora" per alimentare dibattito.
- Valutazione a 48h su impressions/CTR/AVD.

### Mese 2 — Ottimizzazione
- Scalare a 2-3 video/sett. Automatizzare voiceover + caption con template.
- Leggere analytics (traffic source = browse/suggested).
- Affiliate/sponsor solo dopo monetizzazione stabile.

### KPI target ⚠️ (benchmark di nicchia, non del canale)
- CTR ≥ 4-6%
- AVD ≥ 30-40% su long-form
- Soglia "successo" iniziale: ≥ 25-30K views/video
- Rapporto views/iscritti molto alto (nella nicchia ~6x): i video devono performare oltre la base iscritti.

---

## 6. REGOLE DI QUALITÀ (NON NEGOZIABILI — anti copyright/demonetizzazione)
1. Storie **originali** generate da AI, MAI reupload/riassunti di storie già viste.
2. Script **riscritto e rifinito a mano** dall'utente.
3. **Direzione editoriale propria** su montaggio e visual (palette/voce/cornice diverse dal target).
4. **Varietà tra episodi** (non lo stesso ritratto statico riciclato).
5. Trasformazione evidente: replichiamo la STRUTTURA, mai l'ESTETICA del canale target.

---

## 7. LA RACCOMANDAZIONE IN 3 PUNTI
1. **Replica la struttura, NON l'estetica:** copia hook-formula, durata 35-40 min e logica
   thumbnail, ma crea un brand visivo tuo. Riduce il rischio "contenuti inautentici".
2. **Vinci sul gap di qualità:** scene animate per-beat con Higgsfield `generate_video` +
   personaggio coerente + voce espressiva. È il modo più rapido per battere i cloni statici.
3. **Valida sui dati a 48h:** produci 3 episodi, tieni solo gli hook che superano ~25-30K views,
   scala 2-3/sett solo quando CTR e AVD reggono.

---

## 8. PRIMA RICHIESTA DA FARE ALLA CHAT CLAUDE CODE
"Genera lo script del pilota (150 parole) basato su uno dei 10 titoli, poi crea con Higgsfield:
(a) il ritratto del personaggio, (b) 4-5 scene video brevi che riusano lo stesso personaggio,
(c) il voiceover. Infine valuta il risultato con virality_predictor."
