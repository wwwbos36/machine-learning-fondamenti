# Fatal Signal — Voice Notes (Higgsfield Audio)

## Decisione PERMANENTE
- **Audio = Higgsfield** (NON ElevenLabs, mai).
- **Modello: MiniMax Speech 2.8 HD** — scelto per audio più lunghi e continui.
- **Voce: Xavier** (fissa per tutti gli episodi → coerenza brand).
- Generazione fatta nella **UI web di Higgsfield** (feature Speak/Audio): l'integrazione
  MCP di Claude Code NON espone MiniMax/Xavier (espone solo Inworld TTS, sonilo, mirelo),
  quindi questo step è manuale/umano nella web app, non automatizzabile da Claude qui.

## Parametri narrazione (invariati)
- Cadenza: **150–160 parole/minuto**.
- Tono: calmo, autorevole, leggermente melanconico.
- Documentario leggero — racconta, non vende.

## Vietato
- Enfasi drammatica esagerata, esclamazioni.
- Termini clickbait ("incredibile", "shocking", "you won't believe").
- Cambi di volume/eccitazione artificiali.

## Workflow audio per episodio
1. Copia il testo narrato di `script.md` (solo prosa, senza marcatori [B-ROLL]/[GRAFICO]).
2. In Higgsfield → Speak: modello **MiniMax Speech 2.8 HD**, voce **Xavier**.
3. Genera in blocchi lunghi/continui (vantaggio del modello) per ridurre i tagli.
4. Esporta, normalizza a **-16 LUFS** (standard YouTube), 48kHz.
5. Lasciare 0.4–0.6s di pausa ai cambi di capitolo (respiro narrativo).

## Nota tecnica
- Se in futuro servisse un TTS pilotabile da Claude Code via MCP (per automazione),
  l'unico disponibile è `inworld_text_to_speech` — ma la scelta ufficiale resta
  MiniMax 2.8 HD / Xavier nella UI Higgsfield.
