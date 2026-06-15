# 📒 DIARIO DI PROGETTO — Fatal Signal

> **Scopo di questo file:** stato completo e aggiornato del lavoro, così che una
> nuova sessione di Claude Code (anche su un altro account, senza memoria della
> chat) possa importare i file e continuare senza perdere nulla.
> **Aggiornare questo file ad OGNI passo significativo.**

**Ultimo aggiornamento:** 2026-06-15 ~08:55 UTC
**Branch git:** `claude/loving-knuth-pc2kxd`
**Repo path:** `/home/user/machine-learning-fondamenti/fatal-signal/`

---

## 1. COS'È IL PROGETTO
Canale YouTube faceless **"Fatal Signal"**: mini-documentari cinematografici
(12–16 min) sull'ascesa e caduta di marchi **tech/digitali**. Tesi ricorrente:
ogni gigante è crollato per un singolo errore strategico — **"The Fatal Flaw"**.
Stack: **Claude Code** (ricerca/script) · **Higgsfield** (B-roll/intro **+ audio
voiceover: MiniMax Speech 2.8 HD, voce Xavier**) · **DaVinci Resolve** (montaggio
umano). ⚠️ Voce SEMPRE Higgsfield, MAI ElevenLabs (decisione permanente utente).
Lingua video: **inglese**. Cadenza: **1 video/settimana**.

Documenti di riferimento (LEGGERE PRIMA DI LAVORARE):
- `MASTER-PROMPT.md` → manuale operativo, fasi 0–10, comandi.
- `_brand/style-bible.md` → palette, tono, struttura fissa, regole anti-clone.
- `_brand/higgsfield-base-prompts.md` → prompt visivi base.
- `README.md` → overview.

---

## 2. REGOLE DI LAVORO (richieste esplicite dell'utente)
1. ⚠️ **UN EPISODIO ALLA VOLTA.** Finire COMPLETAMENTE un episodio (incl.
   fact-check) prima di iniziare il successivo. NON saltare avanti.
2. ⚠️ **La ricerca va sempre verificata e salvata in `research.md`** prima di
   considerare un episodio "fatto". I fatti `[DA VERIFICARE]` NON sono validi.
3. Aggiornare SEMPRE questo DIARIO.
4. Fact-check umano obbligatorio prima della produzione (regola di sistema).
5. Higgsfield ≤ 40% delle scene; loghi/persone/eventi reali → solo stock.

---

## 3. STATO ATTUALE — riepilogo rapido
| Episodio | Stato | Cosa manca |
|----------|-------|-----------|
| **EP001 Nokia** | 🟢 SCRIPT PRONTO | Fatti ✅ verificati. Script ✅ espanso a ~2.050 parole (testo definitivo). Resta: voiceover Higgsfield (MiniMax 2.8 HD/Xavier); generare B-roll Higgsfield (12 asset); montaggio DaVinci |
| **EP002 BlackBerry** | 🟡 Parziale (avviato troppo presto) | Fatti ✅ verificati; mancano titoli, thumbnail, shotlist, metadata; espandere script. **DA RIPRENDERE SOLO DOPO EP001** |
| EP003 Yahoo | ⚪ Non iniziato | tutto |
| EP004 WeWork | ⚪ Non iniziato | tutto |

**FOCUS IMMEDIATO:** finire EP001 Nokia (espansione script + asset visivi +
voce + montaggio). Titoli/thumb/shotlist/metadata già pronti (FASI 5–8).

---

## 4. FILE CREATI (inventario)

### Struttura base (FASE 0) — ✅ completa, committata e pushata
- `README.md`, `MASTER-PROMPT.md`
- `_brand/`: `style-bible.md`, `higgsfield-base-prompts.md`, `voice-notes.md`, `visual-library.md`
- `_templates/`: `script-template.md`, `title-prompt.md`, `thumbnail-brief-template.md`, `shotlist-higgsfield-template.md`, `metadata-template.md`, `scoring-argomenti.md`
- `_research/`: `argomenti-database.md` (23 marchi con scoring), `argomenti-esclusi.md`
- `calendario.md`, `checklist-pre-pubblicazione.md`, `anti-duplicazione-log.md`

### EP001 Nokia — `episodi/EP001-nokia/`
- `research.md` ✅ **FATTI VERIFICATI con fonti** (Sez. 7). Correzioni applicate: ott 1998 (#1), regno 14 anni fino al 2012, picco ~40% fine 2007, memo Elop ~8 feb vs partnership MS 11 feb, acquisizione €5,44 mld chiusa apr 2014, ricerca Vuori & Huy ASQ 2016, HMD 18 mag 2016.
- `outline.md` ✅
- `script.md` ✅ ~2.050 parole, fatti verificati, narrazione pulita. Punto "prototipi" risolto (Nokia 7710 touchscreen 2004). TESTO DEFINITIVO.
- `audio-script.md` ✅ struttura audio voiceover-ready: 7 blocchi (capitoli), testo solo-narrazione pulito, ~1.810 parole, ~11:40 di parlato. Pronto da incollare in Higgsfield Speak (MiniMax 2.8 HD / Xavier). L'utente genera l'audio.
- `titles.md` ✅ (consigliato #2: "Nokia Saw the Future — And Still Lost Everything")
- `thumbnail-brief.md` ✅ · `shotlist-higgsfield.md` ✅ (9 scene Higgsfield, 33%) · `metadata.md` ✅
- **Tesi EP001:** errore fatale = cultura della paura (la verità non saliva ai vertici; ricerca Huy & Vuori INSEAD).

### EP002 BlackBerry — `episodi/EP002-blackberry/`
- `research.md` ✅ **FATTI VERIFICATI con fonti** (vedi Sezione 7 del file; libro chiave "Losing the Signal")
- `outline.md` ✅
- `script.md` 🟡 ~1.450 parole, fatti aggiornati/verificati (restano 3 cifre contese: quota USA %, market cap, picco ricavi FY2011), da espandere
- titoli / thumbnail / shotlist / metadata → ❌ NON ancora creati
- **Tesi EP002:** errore fatale = scambiare ciò che li rese grandi (tastiera/sicurezza) per ciò che li avrebbe tenuti grandi (dogma identitario). DIVERSA da Nokia (anti-dup ok).

---

## 5. ASSET HIGGSFIELD generati (test stile)
Piano: **Plus**, ~102 crediti residui (erano 121.85; 2 clip da 10 cr generate).
Modello usato: `kling3_0`, 5s, 16:9, ~10 crediti/clip.
- Job `aa799fff-f2f5-419c-b075-1d17be0574dc` → **INTRO-001** (corridoio corporate, dolly-in). Stato: generato (verificare nel workspace Higgsfield).
- Job `753078dd-2860-416f-b561-880929f9a841` → **FEAR-001** (sala riunioni silhouette). Stato: generato (verificare nel workspace).
- ⚠️ `job_display` in chat richiede approvazione permessi: visualizzarli direttamente nel workspace Higgsfield.
- Asset riusabili definiti ma DA GENERARE: RISE-001, FALL-001, TENS-001, THESIS-001, TRANS-001 (+ specifici per episodio: MAP-001, DEVICE-001, APPS-001, PATHS-001, BULB-001).

---

## 6. PROSSIMI PASSI (in ordine — UN EPISODIO ALLA VOLTA)
1. ✅ FATTO — EP001: fatti Nokia verificati (research.md + script.md).
2. ✅ FATTO — EP001: script espanso a ~2.050 parole, narrazione definitiva.
3. **[PROSSIMO] EP001: produzione asset visivi** — generare con Higgsfield i 12
   B-roll della shotlist (INTRO-001 e FEAR-001 già generati come test); reperire
   stock/archivio; voiceover in Higgsfield (MiniMax 2.8 HD, voce Xavier); montaggio DaVinci.
   → poi EP001 = PRONTO/PUBBLICABILE.
4. SOLO DOPO che EP001 è chiuso: riprendere EP002 BlackBerry (titoli, thumb,
   shotlist, metadata, espansione script — i fatti sono già verificati).
5. Poi EP003 Yahoo, EP004 WeWork (4 video in banca prima del lancio).

---

## 7. NOTE / DECISIONI APERTE
- ✅ VOCE DECISA (permanente): **Higgsfield, MiniMax Speech 2.8 HD, voce Xavier**.
  Generazione nella UI web Higgsfield (l'MCP qui espone solo Inworld TTS, non MiniMax).
- Cifre contese BlackBerry da fissare su fonte primaria prima del montaggio.
- Incidenti ricerca: 2 agenti background falliti (limite sessione + handoff malformato). Se ricapita, rilanciare la ricerca e NON procedere con fatti non verificati.
