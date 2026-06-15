# Fatal Signal — Faceless YouTube Channel System

Mini-documentari cinematografici (12–16 min) sull'ascesa e caduta dei marchi
tech e digitali. Tesi editoriale ricorrente: **ogni gigante è crollato per un
singolo errore strategico evitabile — "The Fatal Flaw".**

## Stack
- **Claude Code** → ricerca, scripting, titoli, metadata, shotlist, anti-duplicazione
- **Higgsfield** → B-roll cinematografico + intro firma **+ audio voiceover (MiniMax Speech 2.8 HD, voce Xavier)**
- **DaVinci Resolve** → montaggio finale (supervisione umana)

## Parametri canale
| Campo | Valore |
|---|---|
| Nicchia | Marchi tech e digitali (declino/trasformazione) |
| Target | Uomini 25–55, anglofoni Tier-1, alto valore pubblicitario |
| RPM stimato | $4–24 (tech) |
| Frequenza | 1 video/settimana (policy-safe, qualità > volume) |
| Durata | 12–16 min |
| Lingua video | Inglese |

## Struttura repo
```
fatal-signal/
├── _templates/   → template riutilizzabili per ogni fase
├── _brand/       → style bible, voce, libreria visiva, prompt Higgsfield base
├── _research/    → database argomenti + esclusioni
├── episodi/      → un sottocartella per episodio (EP[NNN]-[nome])
├── calendario.md
├── checklist-pre-pubblicazione.md
└── anti-duplicazione-log.md
```

## Comandi operativi (vedi MASTER-PROMPT.md)
| Comando | Azione |
|---|---|
| `setup repo` | Esegue FASE 0 (questa struttura) |
| `scoring [azienda]` | FASE 1 — selezione e scoring argomento |
| `script [azienda]` | FASI 2–4 — research, outline, script |
| `pacchetto completo [azienda]` | FASI 1–9 complete |
| `inizia EP[NNN]` | FASI 1–8 in sequenza con checkpoint umani |

## Regole d'oro
1. Mai generico: ogni episodio ha una tesi specifica.
2. Il fact-check umano non è opzionale (linea tra monetizzazione e ban).
3. "The Fatal Flaw" presente in OGNI episodio.
4. Ogni video deve superare il test "è chiaramente diverso da tutti gli altri?".
5. Higgsfield è leva visiva, non sostituto del contenuto.
6. Identità editoriale > volume: 1 video/settimana, mai daily.
7. Costruisci come un brand, non come una content farm.
