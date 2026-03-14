# Priority TODO / Fix List

## P0 (Most Important)
- [x] Fix Python syntax/runtime blockers in `The code` so the script runs end-to-end.
- [x] Replace unsupported GPU string hashing behavior with reliable CPU SHA-256 hashing.
- [x] Add GPU-to-CPU fallback for statistical operations when CUDA is unavailable.

## P1 (High)
- [ ] Rename `The code` to `mining_ai.py` for standard Python tooling and discoverability.
- [ ] Add automated tests for hashing output and statistics correctness.
- [ ] Add `requirements.txt` and optionally `pyproject.toml`.

## P2 (Environment / Deployment)
- [x] Document Windows + WSL + Python + Rust + ngrok setup workflow.
- [ ] Add a small HTTP app/example endpoint on `:8080` for ngrok demos.
- [ ] Automate release zip generation for "IP custody platform" snapshots.

## P3 (Polish)
- [ ] Add PNG/ICO exports from SVG brand assets.
- [ ] Add CI workflow that runs lint/type-check/tests.
