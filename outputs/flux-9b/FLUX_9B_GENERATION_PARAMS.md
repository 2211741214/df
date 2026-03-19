# FLUX 9B Generation Parameters

Generated at: `2026-03-18 14:29:22 UTC`  
Project root: `/home/1011lr/dfmodel`

## 1) Model / Service

- Backend: `diffusers` (non-ComfyUI inference)
- Model ID: `black-forest-labs/FLUX.2-klein-9B`
- API endpoint used by batch: `http://127.0.0.1:9000/generate`
- Device: `cuda` (from `app.py` default)
- API output dir during this run: `/home/1011lr/dfmodel/outputs/flux-9b`

Service launch pattern (redacted):

```bash
HF_TOKEN=<redacted> BACKEND=diffusers MODEL_ID=black-forest-labs/FLUX.2-klein-9B \
OUTPUT_DIR=/home/1011lr/dfmodel/outputs/flux-9b \
python -m uvicorn app:app --host 0.0.0.0 --port 9000
```

## 2) Batch Generation Args

Script: `/home/1011lr/dfmodel/scripts/batch_generate_flux_from_excel.py`

- `--excel /home/1011lr/dfmodel/task.xlsx`
- `--id-column task_id`
- `--prompt-column prompt_en`
- `--output-dir /home/1011lr/dfmodel/outputs/flux-9b`
- `--api-url http://127.0.0.1:9000/generate`
- `--repeat 3`
- `--width 1024`
- `--height 1024`
- `--steps 15`
- `--guidance 1.0`
- `--timeout 600`
- `--overwrite true`

Output naming:

- `{task_id}_{run_index}.png`
- Example: `T001_1.png`, `T001_2.png`, `T001_3.png`

## 3) Result Summary

- Valid task rows in `task.xlsx`: `154`
- Expected images: `154 * 3 = 462`
- Actual images (`T*_[123].png`): `462`
- Missing images: `0`

Observed file timestamp range (UTC):

- First output: `2026-03-18 01:28:38 UTC`
- Last output: `2026-03-18 03:00:21 UTC`

## 4) Notes

- HF token was used for gated model access, but token value is intentionally not recorded in this document.
- This document only captures the generation configuration and final output checks for this run.
