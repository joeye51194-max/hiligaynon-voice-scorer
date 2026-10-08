# hiligaynon-voice-scorer

Accent-robust **Hiligaynon / Taglish ASR + speech scoring** built on self-recorded data, fine-tuned from open speech encoders (MMS adapters / wav2vec2 / Whisper), and served behind Telnyx Voice AI via Media Streams.

This is portfolio proof-of-work for applied speech-ML roles. It deliberately mirrors the discipline of a real speech team: **gold eval set first → fine-tune → shadow-deploy → publish honest results** — including the failures.

## Status

**Phase 0 — Foundations** · started 2026-10-08 · target: ~6–8 weekends · budget: <$50 total

| Phase | Deliverable | Status |
|---|---|---|
| 0 | Repo scaffold + accounts | 🔄 in progress |
| 1 | Dataset "Hiligaynon Speech v0" (3–5 hrs, 3–5 speakers) | — |
| 2 | Honest baseline: MMS / Whisper / Omnilingual WER on test set | — |
| 3 | Fine-tune (MMS adapters / wav2vec2 / Whisper) → ONNX distill | — |
| 4 | Scoring layer (speechocean762 head) + accent-robustness eval | — |
| 5 | Serving: FastAPI + Telnyx Media Streams (PCMU 8 kHz → wss) | — |
| 6 | Real calls, demo video, publish model+dataset+write-up | — |
| 7 | Stretch: code-switch scoring, fairness calibration, alignment | — |

## Repository layout

```
data/      # recordings, manifests, transcriptions (audio itself lives outside git / LFS)
scripts/   # manifest builder, QC, training, eval
models/    # checkpoints, ONNX exports (not committed)
serving/   # FastAPI + WebSocket service for Telnyx media streams
docs/      # consent forms, normalization rules, experiment notes
```

## Rules (project law)

1. Personal recordings only — never work/customer audio or systems.
2. Written speaker consent **before** publishing anything.
3. Speaker-disjoint train/dev/test, always. No vanity metrics.
4. Every failed experiment gets logged in `docs/experiments.md` — that's the interview gold.

## Results

Baseline WER/CER table lands here after Phase 2. Honest numbers only.
