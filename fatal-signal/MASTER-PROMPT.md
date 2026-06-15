# FATAL SIGNAL — Master Operational Prompt (v1.0)

Manuale operativo del canale faceless "Fatal Signal". Questo file è la fonte di
verità per l'orchestrazione con Claude Code.

## Identità progetto
Mini-documentari cinematografici (12–16 min) sull'ascesa e caduta di marchi tech
e digitali. Tesi ricorrente: ogni gigante è crollato per un singolo errore
strategico evitabile — **"The Fatal Flaw"**.

Stack: Claude Code (ricerca/script/titoli/metadata/shotlist) · Higgsfield (B-roll
+ intro + audio voiceover, MiniMax Speech 2.8 HD voce Xavier) · DaVinci Resolve
(montaggio umano). NB: voce = sempre Higgsfield, MAI ElevenLabs.
Target: uomini 25–55, anglofoni Tier-1. RPM $4–24. 1 video/settimana. Lingua: inglese.

## Comandi
| Comando | Azione |
|---|---|
| `setup repo` | FASE 0 — struttura + file brand/template (FATTO ✅) |
| `scoring [azienda]` | FASE 1 — selezione e scoring |
| `script [azienda]` | FASI 2–4 — research → outline → script |
| `pacchetto completo [azienda]` | FASI 1–9 |
| `inizia EP[NNN]` | FASI 1–8 in sequenza, con checkpoint umano dopo FASE 2 (fact-check) e FASE 4 (review script) |

## Fasi
- **FASE 0 — Setup repo:** struttura cartelle + file `_brand/`, `_templates/`, `_research/`, root.
- **FASE 1 — Selezione:** scoring composito, anti-dup, anti-clone → report ~200 parole (`_templates/scoring-argomenti.md`).
- **FASE 2 — Research:** `episodi/EP[NNN]-[nome]/research.md` (timeline, dati, errore fatale, cause, competitor, oggi, fonti, note). ⚠️ ogni fatto con fonte; senza fonte → `[DA VERIFICARE]`. **Checkpoint umano.**
- **FASE 3 — Outline:** `outline.md` con la struttura fissa (Hook→Origini→Ascesa→Errore→Caduta→Oggi→Riflessione) e timing.
- **FASE 4 — Script:** `script.md` 1.800–2.300 parole, marcatori `[B-ROLL]`/`[GRAFICO]`, errore in grassetto, ultima riga "The fatal flaw was…". **Checkpoint umano.**
- **FASE 5 — Titoli:** `titles.md` 8 varianti (formule A/B/C/D) con scoring.
- **FASE 6 — Thumbnail:** `thumbnail-brief.md` (variante A/B).
- **FASE 7 — Shotlist:** `shotlist-higgsfield.md` (≤40% AI, persone/loghi/eventi → stock).
- **FASE 8 — Metadata:** `metadata.md` (titolo, descrizione + disclosure AI, tag, capitoli).
- **FASE 9 — Anti-duplicazione:** confronto con archivio, report similarità, aggiorna `anti-duplicazione-log.md`.
- **FASE 10 — Calendario:** aggiorna `calendario.md`.

## Sequenza di lancio (4 video in banca)
EP001 Nokia · EP002 BlackBerry · EP003 Yahoo · EP004 WeWork.

## Regole globali
1. Mai generico: tesi specifica per episodio.
2. Fact-check umano non opzionale (linea monetizzazione/ban).
3. "The Fatal Flaw" in OGNI episodio.
4. Test "è chiaramente diverso da tutti gli altri?".
5. Higgsfield = leva visiva, non sostituto del contenuto.
6. Identità editoriale > volume: 1 video/settimana, mai daily.
7. Costruisci come un brand, non come una content farm.

## Cosa NON automatizzare mai
Fact-check finale · editing ritmo script · scelta titolo definitivo · montaggio
finale · controllo policy. L'AI produce, l'umano decide.
