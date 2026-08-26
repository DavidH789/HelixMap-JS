# HelixMap-JS

**Hierarchical Admixture & PCA Stability Lab** — browser-only tool for continent → region → population **genetic signal** from consumer raw DNA (23andMe / AncestryDNA / MyHeritage / VCF-style text).

> **Not genealogical ancestry percentages.** Numbers are model contributions under the current reference panel (REAL 1000G + literature + blend proxies), with explicit quality weighting and validation diagnostics.

[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)
<!-- After Zenodo: [![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.XXXXXXX.svg)](https://doi.org/10.5281/zenodo.XXXXXXX) -->

## Features

- **Hierarchical EM**: continents → regions → populations (region-first EUR to reduce NW_EUR leakage)
- **Frequency quality weighting**: REAL 1000G (1.0) > literature APPROX (0.80) > BLEND (0.30) > proxy
- **PCA (v17+)**: LD-pruning + √Rosenberg *Iₙ* weights, PC1–PC3, Procrustes stability lab
- **Validation**: real NYGC 30× 1000G individuals, hold-out / LOO benchmarks, self-simulation
- **Privacy**: all computation **client-side**; optional local DNA cache (IndexedDB) with one-click delete
- **Lab UI**: quality inventory, robustness / model trust, Full model vs REAL-only comparison

## Quick start

1. Download [`index.html`](index.html) (or clone this repo).
2. Open in **Chrome / Firefox / Safari** (on iPhone: Share → Open in Safari, not Files preview).
3. Drop a raw DNA `.txt` / `.csv` / `.zip`.
4. Optional: leave **“Зберігати файл локально”** checked so the next visit restores from browser IndexedDB; use **Видалити збережені дані** to clear.

No server, no account, no upload.

## What it is / is not

| Is | Is not |
|----|--------|
| Model contribution / genetic signal map | Clinical or forensic report |
| Open methodology + benchmarks | “X% Ukrainian blood” genealogy |
| Local-only processing | Cloud DNA analysis |

Country-level proxies (POL/UKR/…) are often genetically close; treat weak country % with caution. Strong regional / continental signals are more reliable.

## Methods (short)

- **Likelihood**: supervised-style EM on allele frequencies; SNPs weighted by reference quality and informativeness.
- **Hierarchy**: continent EM → region EM (EUR split: NW / E / S / SE / JEW) → population EM inside strong regions.
- **PCA**: frequency matrix only (labels not in the Gram matrix); LD-pruned panel; stability via hold-out, LOPO, Procrustes.
- **Benchmarks**: embedded real 1000G genotype vectors (NYGC high-coverage subset) for LOO / hold-out; self-sim for upper bound only.

See in-app **Лабораторія** tabs and changelog for version history (v17–v18.5).

## Privacy

- Raw genotypes never leave the device.
- Optional cache uses **IndexedDB** in your browser only.
- Clear via the in-app button or browser site data settings.

## Citation

If you use HelixMap-JS in coursework, research, or applications (e.g. FLEX / UWC portfolio), please cite the Zenodo DOI once published:

```
David (@DavidH789). HelixMap-JS: Hierarchical Admixture & PCA Stability Lab (browser).
Version 18.5. https://github.com/DavidH789/helixmap-js
```

`CITATION.cff` will be updated with the DOI after the first Zenodo release.

## License

Code: **MIT** (see [LICENSE](LICENSE)).

Reference allele frequencies and embedded 1000 Genomes–derived materials remain under their original public data terms (1000 Genomes / NYGC and cited literature). This repository does not claim ownership of those data.

## Author

**David** ([@DavidH789](https://github.com/DavidH789)) — front-end developer (HTML / CSS / JavaScript).  
Related: [HelixOne](https://github.com/DavidH789/HelixOne) (multi-provider DNA ethnicity report merger).  
Open science / portfolio project (2026). Issues and PRs welcome after public release.

## Roadmap (optional)

- [x] English UI toggle (UA | EN)
- [ ] Modular JS split (engine vs UI)
- [ ] Export JSON/CSV results
- [ ] Zenodo DOI + CITATION.cff update
- [ ] Minimal offline service worker (app shell only; DNA stays in IndexedDB)
