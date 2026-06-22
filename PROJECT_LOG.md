# PROJECT LOG — Size Up Animation (reverse engineering + replica canale YouTube)

> Questo file viene aggiornato ad ogni passo importante della sessione.
> Serve a permettere a qualsiasi istanza di Claude Code di riprendere il lavoro senza perdere contesto.
> È autosufficiente: leggendo solo questo file si capisce tutto.

***

## 📌 STATO ATTUALE
- **Ultimo aggiornamento:** 2026-06-20
- **Fase corrente:** ✅ VIDEO TREVOR vs SCP (set 'trevorscp', 40 entita') a **4:40** (7s/char), scala 1,6m→900m (climax SCP-3000 Anantashesha). `video\trevor_vs_scp_final.mp4`.
- **Video pronti in `video\`:** poppy_playtime_final, the_boiled_one_final, trevor_vs_scp_final.
- **Prossimo step da fare:** SFX whoosh/boom sui reveal + intro hook/outro CTA + logo. Poi prossimo set IP (Digital Circus / Backrooms / Skibidi).
- **CONVENZIONI NUOVE:** (1) i video FINITI vanno in `SizeUp_Analysis\video\`. (2) durata target 3-5 min: usare `--minutes 4` (SCENE auto = minuti*60/N personaggi). (3) la musica viene messa in LOOP (-stream_loop) se piu' corta del video.

***

## 🎯 OBIETTIVO DEL PROGETTO
Fare reverse engineering del canale YouTube faceless **Size Up** (@SizeUpAnimation) — esploso con 8 video / ~930K views — e **replicarne il format** per creare un canale analogo. Nicchia: *horror/creepypasta-gaming "size comparison"* (silhouette nere di mostri con occhi rossi su cielo grigio + griglia di scala). Tutta la produzione deve avvenire **senza spendere crediti Higgsfield ("token") né token a pagamento**: immagini via seedream unlimited, audio via tool locali.

***

## ✅ PROGRESSI COMPLETATI
| # | Cosa abbiamo fatto | Data | Note |
|---|-------------------|------|------|
| 1 | Analisi completa del canale (7 fasi) via browser, dati reali | 2026-06-20 | Report `SizeUpAnimation_Reverse_Engineering.md` |
| 2 | Verifica AUDIO: scaricato (yt-dlp) + trascritto (faster-whisper locale) 3 video | 2026-06-20 | Scoperto: **nessun voiceover**, solo musica + SFX |
| 3 | Risolto slug Higgsfield cambiato + pipeline seedream unlimited | 2026-06-20 | `seedream_v4_5`→**`seedream_v5_lite`** (quality+seed) |
| 4 | Generato set TEST (3 silhouette) — pipeline validata, 0 crediti | 2026-06-20 | `images/test*.png` |
| 5 | Generato set completo **Trevor Henderson** (8 silhouette ordinate) | 2026-06-20 | `images/trevor/01..08.png` |
| 6 | Generato 6 riferimenti di scala + cutout trasparenti | 2026-06-20 | `images/scale_refs/` + `images/scale_refs_cutout/` |
| 7 | Creata thumbnail finale "???M" stile canale | 2026-06-20 | `images/thumb/thumbnail_FINAL.png` |
| 8 | Selezionate fonti musica horror royalty-free | 2026-06-20 | Pixabay (consigliata), Uppbeat, Fesliyan |
| 9 | Adottato approccio MODULARE (mostri/sfondo/compositing separati) | 2026-06-20 | Decisione su brief utente |
| 10 | Generati 8 mostri su sfondo BIANCO (isolabili) + sfondo permanente | 2026-06-20 | `assets/monsters_raw/`, `assets/background/bg_main.png` |
| 11 | Creati cutout trasparenti ritagliati dei mostri | 2026-06-20 | `assets/monsters/monster_01..08.png` |
| 12 | Libreria compositing parametrica + anteprima statica validata | 2026-06-20 | `compose_lib.py`, `images/preview_compositing.png` |
| 13 | Scritto template render video (animazione + zoom-out) | 2026-06-20 | `compose_video.py` |
| 14 | Sagome mostri rese ERETTE (clausola: naturali se non bipedi) | 2026-06-20 | Rigenerati 8 mostri + cutout |
| 15 | Installato imageio + imageio-ffmpeg (render, no ffmpeg di sistema) | 2026-06-20 | ffmpeg bundlato nel pacchetto |
| 16 | RENDER v1 1080p con musica utente | 2026-06-20 | `video_draft_music.mp4` (28s, H264+AAC) |
| 17 | Riscritto motore layout ANTI-SOVRAPPOSIZIONE (fit altezza+larghezza) | 2026-06-20 | Risolti overlap inizio/worm; fade musica in/out |
| 18 | Generate immagini personaggio a colori (riquadri) | 2026-06-20 | `assets/refs_char/monster_01..08.png` (gen_char_refs.py) |
| 19 | Video: riquadro immagine + nome/altezza sopra la sagoma + m/ft | 2026-06-20 | make_card in compose_video.py; v3 renderizzato |
| 20 | FIX cutout (bbox solo su pixel scuri) -> altezze = griglia | 2026-06-20 | build_cutouts.py; verificato con check_align.py (diff 1px) |
| 21 | v4: nome+altezza TESTO sopra sagoma; immagine ref SENZA testo nel punto libero | 2026-06-20 | free_spot()+_text_img() in compose_video.py |
| 22 | Immagine di riferimento raddoppiata (20%->40% larghezza) | 2026-06-20 | box_w=W*0.40 in compose_video.py |
| 23 | Analisi canale phantomized + confronto + 10 idee video | 2026-06-20 | `PHANTOMIZED_and_10_Ideas.md` (108K sub, 29 video, 41M views) |
| 24 | Sistema MULTI-SET (env SIZEUP_SET) — scheletro invariato, cambiano solo asset+CATALOG | 2026-06-20 | compose_lib CATALOGS{} + dir per set; build_cutouts/compose_video set-aware |
| 25 | Generati asset POPPY PLAYTIME (8 sagome + 8 ref) + render | 2026-06-20 | `gen_poppy.py`; `assets/sets/poppy/`; `poppy_playtime_final.mp4` |
| 26 | Gestito filtro NSFW seedream (crediti rimborsati): riformulato prompt doll | 2026-06-20 | vedi memoria higgsfield-nsfw-reformulate |
| 27 | Poppy esteso a 14 personaggi + durata configurabile (--minutes) | 2026-06-20 | SCENE=min*60/N; ZOOM continuo; scena1 zoom-out |
| 28 | Fix audio: loop musica (-stream_loop) -> niente taglio a durata traccia | 2026-06-20 | finale ora 4:00:00 esatti |
| 29 | VIDEO FINALE 4 min in `video\poppy_playtime_final.mp4` | 2026-06-20 | 1080p/30fps, 14 char, musica loop+fade |
| 30 | Poppy esteso a **35 personaggi** + ritmo piu' veloce (~7s/char) | 2026-06-20 | CATALOG 35; gap adattivo; fix scaled() min 1px |
| 31 | PERF: cache immagini sorgente (_SRC_CACHE / _REF_CACHE) ~9x render | 2026-06-20 | render 4min/35char in ~5-6 min invece di 30+ |
| 32 | NUOVO LAYOUT: soggetto corrente sempre grande (height-fit + ancoraggio CX_CUR, cap larghezza); ref sempre on-screen a sinistra | 2026-06-20 | risolti: ref tagliata/che copre, figure troppo piccole a fine video |
| 33 | SET 'boiled' (40 creature) + video THE BOILED ONE 4:40 @7s/char | 2026-06-21 | `gen_boiled.py`, CATALOGS['boiled'], `video\the_boiled_one_final.mp4` |
| 34 | NOTA: passare la musica a compose_video con percorso WINDOWS (os.path.exists fallisce su /c/...), altrimenti salta il mux | 2026-06-21 | gen in background puo' bloccarsi: usare waiter (Monitor/until) per ripartire |
| 35 | SET 'trevorscp' (40 entita' Trevor+SCP) + video TREVOR vs SCP 4:40 @7s/char | 2026-06-21 | `gen_trevorscp.py`, CATALOGS['trevorscp'], `video\trevor_vs_scp_final.mp4` |
| 36 | SET 'circus' (36, Digital Circus) + video 4:12 @7s/char | 2026-06-21 | `gen_circus.py`, CATALOGS['circus'], `video\digital_circus_final.mp4` |
| 37 | FIX layout: nome disegnato SOPRA l'immagine + free_spot overlap*100 (mai copre sagome/nome). Ri-renderizzati circus/boiled/trevor | 2026-06-21 | risolto: prime 2 sagome coperte dalla ref |
| 38 | REGOLA UTENTE: immagine di riferimento SEMPRE FISSA in alto a sinistra (gx=2%W, gy=3%H). free_spot non piu' usato | 2026-06-21 | compose_video.py |
| 39 | SET 'backrooms' (38 entita') + video BACKROOMS 4:26 @7s/char | 2026-06-21 | `gen_backrooms.py`, `orchestrate_backrooms.sh` (auto-restart), `video\backrooms_final.mp4` |
| 40 | SET 'skibidi' (36) + video SKIBIDI 4:12 @7s/char | 2026-06-21 | `gen_skibidi.py`; risolti hang+NSFW (monster_02) + chrome pw_profile bloccati; `video\skibidi_final.mp4` |
| 41 | FIX pipeline: download ROBUSTO (urlopen+open wb), kill SOLO chrome pw_profile, orchestratore con watchdog anti-hang | 2026-06-21 | `fix_skibidi_02.py`, `orchestrate_residentevil.sh` |
| 42 | SET 'residentevil' (38) + video RE 4:26 @7s/char | 2026-06-21 | `gen_residentevil.py`+orchestratore watchdog (0 blocchi); `video\residentevil_final.mp4` |
| 43 | SET 'kaiju' (36, Godzilla/Monsterverse) + video 4:12 @7s/char | 2026-06-21 | `gen_kaiju.py`+`orchestrate_kaiju.sh`; `video\kaiju_final.mp4` |
| 44 | SET 'banban' (36, Garten of Banban) + video 4:12 @7s/char | 2026-06-22 | `gen_banban.py`+orchestratore; NSFW monster_06 riformulato; `video\banban_final.mp4` |
| 46 | SET 'lovecraft' (36, Cthulhu Mythos) + video 4:12 @7s/char, climax Azathoth 2500m | 2026-06-22 | `gen_lovecraft.py`; waiter affidabile OK; `video\lovecraft_final.mp4` |
| 47 | SET 'analoghorror' (36) + video 4:12 @7s/char | 2026-06-22 | `gen_analoghorror.py`; check via allarmi 19min ri-armati (affidabili); `video\analoghorror_final.mp4` |
| 48 | Batch 9 video (rosters.py+gen_generic.py+orchestrate_all.sh). Fatto MINECRAFT (12 totali). | 2026-06-22 | sistema generico multi-set |
| 49 | BLOCCO Datadome: dopo ore di gen automatica Higgsfield risponde 403 (anti-bot) all'API fnf. NON e' la sessione (login ok). Aggravato da launch headless ravvicinati. | 2026-06-22 | `retry_batch.sh` (cooldown 45min + test_api.py + resume) |
| 50 | NOTA: la sessione Higgsfield scade dopo ~ore -> `login_higgsfield.py` (headed, profilo pw_profile che ha la clearance datadome). Profilo NUOVO non ha datadome per fnf. | 2026-06-22 | re-login nel profilo pw_profile, non in uno nuovo |
| 45 | FIX CHECK PERIODICI: il Monitor a sleep lungo (19 min) muore durante il silenzio (terminato come inattivo) -> check non scattano. SOLUZIONE: usare task in background che ESCONO (sleep+stato) -> la notifica di COMPLETAMENTO task e' affidabile; ri-armare un allarme da ~19 min + un waiter sul file finale | 2026-06-22 | NON usare Monitor persistente per i check; usare waiter/allarmi |

***

## 🗂️ STRUTTURA DEL PROGETTO
Root progetto: `C:\Users\ramon\Desktop\claude\SizeUp_Analysis\`
```
PROJECT_LOG.md                         <- questo file
SizeUpAnimation_Reverse_Engineering.md <- report analisi completo (7 fasi)
sizeup_generate.py    <- genera silhouette mostri DENTRO scena (vecchio, set trevor/)
sizeup_assets.py      <- genera riferimenti di scala + base thumbnail
gen_modular.py        <- [MODULARE] genera mostri su BIANCO + sfondo permanente
build_cutouts.py      <- [MODULARE] mostri bianco -> cutout trasparenti ritagliati
compose_lib.py        <- [MODULARE] libreria compositing (bg+griglia+scala+CATALOG mostri)
compose_preview.py    <- [MODULARE] anteprima statica (valida il sistema)
compose_video.py      <- [MODULARE] render video animato (richiede imageio-ffmpeg)
postprocess.py        <- cutout riferimenti + testo "???M" thumbnail
transcribe.py         <- trascrive audio con faster-whisper (patch SSL inclusa)
probe_*.py            <- usa-e-getta per scoprire slug/parametri Higgsfield
audio/                <- audio scaricati dei video Size Up (.webm)
assets/               <- [MODULARE] ASSET RIUTILIZZABILI del sistema
  monsters_raw/       <- mostri su sfondo bianco (monster_01..08.png)
  monsters/           <- mostri cutout trasparenti ritagliati (USATI dal compositing)
  background/bg_main.png <- sfondo permanente riutilizzabile
images/
  trevor/01..08.png   <- vecchio set creature dentro scena (non modulare)
  scale_refs_cutout/  <- riferimenti scala trasparenti (incl. ref_human_1_8m)
  thumb/thumbnail_FINAL.png
  preview_compositing.png <- anteprima del sistema modulare
```

### COME RIUSARE IL SISTEMA PER UN NUOVO VIDEO (altra IP)
1. In `gen_modular.py` cambiare la lista `MONSTERS` (nomi+descrizioni) e lanciare `py gen_modular.py monsters`.
2. `py build_cutouts.py` per i cutout trasparenti.
3. In `compose_lib.py` aggiornare `CATALOG` (file, altezza in metri, nome).
4. `py compose_preview.py` per controllare, poi `py compose_video.py --music <traccia>`.
Lo sfondo `bg_main.png` si riusa per tutti i video.

### SISTEMA MULTI-SET (per nuove IP senza toccare lo scheletro)
Lo SCHELETRO (timing/zoom/musica/layout in compose_video.py) e' UNICO e invariato. Per un nuovo video cambiano SOLO asset + CATALOG, selezionati via variabile d'ambiente `SIZEUP_SET`:
- `trevor` (default): asset in `assets/monsters` + `assets/refs_char`.
- altri set (es. `poppy`): asset in `assets/sets/<set>/monsters` + `.../refs_char`.
- `CATALOG` per set definito in `compose_lib.py` -> `CATALOGS{}`.
Flusso nuovo set (PowerShell, una riga perche' l'env non persiste tra comandi):
1. `py gen_<set>.py` (genera sagome bianco + ref nel set dir)
2. `$env:SIZEUP_SET="<set>"; py build_cutouts.py`
3. `$env:SIZEUP_SET="<set>"; py compose_video.py --fast --out <set>` (bozza)
4. `$env:SIZEUP_SET="<set>"; py compose_video.py --music <traccia> --out <set>` (finale -> <set>_final.mp4)
Output naming: `<out>_draft.mp4` (fast), `<out>.mp4` (muto), `<out>_final.mp4` (con musica).

***

## ⚙️ CONFIGURAZIONI E VARIABILI IMPORTANTI
- **Higgsfield (immagini, 0 crediti):** pipeline browser Playwright + Chrome persistente.
  - Cookie: `C:\Users\ramon\Desktop\claude\_Script_e_Tool_Comuni\higgsfield_cookies.json`
  - Profilo: `_Script_e_Tool_Comuni\pw_profile`
  - Endpoint: `POST https://fnf.higgsfield.ai/jobs/v2/seedream_v5_lite` (token Clerk live dalla pagina)
  - Body params obbligatori: `prompt, width, height, batch_size:1, aspect_ratio, quality:'high', seed (<=1000000), use_unlim:true, resolution:'1k'` + `use_unlim:true` a livello root.
  - Polling: `GET https://fnf.higgsfield.ai/jobs?size=120` → `results.raw.url`.
- **Python:** usare `py` (PowerShell), NON `python` da Git Bash (stub Store). Pacchetti: playwright, faster_whisper, yt-dlp (installato), Pillow.
- **SSL rotto nell'ambiente:** yt-dlp → `--no-check-certificates`; faster-whisper → patch httpx `verify=False` (già in transcribe.py); pipeline browser → `ignore_https_errors=True`.
- **Nessuna API key a pagamento usata.** Nessun ElevenLabs (non serve: canale senza voiceover).

***

## 🐛 PROBLEMI RISOLTI
| Problema | Soluzione adottata | Data |
|----------|-------------------|------|
| `python` non trovato in Git Bash | Usare `py` in PowerShell | 2026-06-20 |
| yt-dlp / HuggingFace: SSL CERTIFICATE_VERIFY_FAILED | `--no-check-certificates` / patch httpx verify=False | 2026-06-20 |
| Slug `seedream_v4_5` → 400 "Unsupported" | Slug attuale **`seedream_v5_lite`** (sonde probe_*.py) | 2026-06-20 |
| 422 missing `quality` / `seed` | Aggiunti `quality:'high'` e `seed`<=1.000.000 | 2026-06-20 |
| 403 Cloudflare intermittenti sul submit | Retry automatico (fino a 4-5 tentativi) | 2026-06-20 |
| Audio: ipotesi voiceover AI non verificata | Trascrizione locale → confermato NESSUN voiceover | 2026-06-20 |

***

## ⚠️ PROBLEMI APERTI / TODO
- [ ] Tarare le altezze in metri del `CATALOG` (valori attuali approssimati dalla lore)
- [ ] Aggiungere SFX "boom" sui reveal grossi (#6/#7/#8)
- [ ] Allungare le scene (~30-45s totali) se serve piu' respiro

### 🎯 GAP STRUTTURALE vs Size Up (analisi 2026-06-20)
Per assomigliare davvero ai video di Size Up mancano:
- [x] **Immagine di riferimento per ogni mostro** (riquadro sul mostro corrente) — FATTO v3
- [x] **Etichetta ancorata alla sagoma** (nome+altezza sopra ogni figura) — FATTO v3
- [x] **Altezza in METRI e PIEDI** (es. "12 m / 39 ft") — FATTO v3
- [ ] **Durata realistica**: Size Up = 3:25–4:25 con ~10-15 personaggi; noi 28s/8 -> servono piu' mostri e scene piu' lunghe.
- [ ] **SFX whoosh/boom** ad ogni entrata (oltre alla musica).
- [ ] **Intro hook** (teaser del piu' grande) + **outro/CTA** (subscribe/end screen).
- [ ] **Logo/watermark** del canale in un angolo.
- [ ] **Numero animato** che "conta" fino all'altezza al reveal (nice-to-have).
- [ ] Decidere nome/branding del NUOVO canale (non clonare troppo "Size Up")
- [ ] (Opz.) generare set per altre IP: mostri marini, Digital Circus/Poppy Playtime

## ✅ RISOLTI in questa sessione (erano TODO)
- [x] Dipendenza render installata (imageio-ffmpeg)
- [x] Musica utente integrata: `C:\Users\ramon\Downloads\alex-morgan-horror-thriller-545512.mp3`
- [x] Render bozza + finale eseguiti
- [x] Sagome mostri ora erette
- [x] SOVRAPPOSIZIONI risolte (layout affiancato/centrato con fit altezza+larghezza)
- [x] Creature larghe (worm) gestite dal fit di larghezza (niente overlap)
- [x] Fade-in/out musica
- [x] Altezza scritta = altezza sulla griglia (fix cutout bbox)
- [x] Nome+altezza come TESTO sopra la sagoma (no testo sull'immagine ref)
- [x] Immagine di riferimento mai sopra le sagome (free_spot)

***

## 📋 DECISIONI PRESE
- **Immagini con seedream_v5_lite unlimited** (non MCP `generate_image` né API `nano_banana`, che consumerebbero crediti). Se mai servissero modelli a pagamento o generazione VIDEO, AVVISARE l'utente PRIMA.
- **Niente voiceover/ElevenLabs**: verificato che il canale di riferimento usa solo musica + SFX → format più semplice ed economico.
- **IP di partenza: Trevor Henderson** (scelta dall'utente: altissimo volume di ricerca, core del canale).
- **Stile immagini**: silhouette nera + occhi rossi + cielo grigio nuvoloso + griglia orizzontale + riferimento di scala (omino/auto/edificio).
- **Musica**: preferire **Pixabay** (gratis, senza attribuzione, sicura per Content ID); evitare CC generiche di SoundCloud.
- **Organizzazione**: tutto dentro la sottocartella di progetto `SizeUp_Analysis\`.
- **Architettura MODULARE (2026-06-20)**: asset separati da timeline. Mostri = cutout trasparenti isolati su bianco; sfondo = plate permanente unico riutilizzabile; griglia di misura disegnata in codice (nitida); scala guidata dall'altezza reale in metri (`CATALOG`). Sostituire un video = cambiare lista mostri + CATALOG, lo sfondo resta. Render via PIL (frame) + imageio-ffmpeg (encode), niente ffmpeg di sistema.
- **Audio**: musica come unica base (loop, fade in 2s / fade out 3s), 1-2 SFX horror sui reveal grossi; nessuna narrazione. Durata musica = durata video (taglio con `-shortest`).

***

## 🔗 RISORSE E RIFERIMENTI
- Canale analizzato: https://www.youtube.com/@SizeUpAnimation
- Competitor leader del format: **phantomized** (8.7M/3.4M views), MetaBallStudios (13M), Size Lab, BlackScale Studio.
- Musica royalty-free: Pixabay Music; Uppbeat; Fesliyan ([dark ambient](https://www.fesliyanstudios.com/royalty-free-music/downloads-c/dark-ambient-music/76), [scary horror](https://www.fesliyanstudios.com/royalty-free-music/downloads-c/scary-horror-music/8)).
- Memoria Claude correlata: `broll-seedream-chrome` (aggiornata con il nuovo slug), `higgsfield-credit-rules`.
