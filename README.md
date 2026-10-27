# HelixMap-JS

[![DOI](https://zenodo.org/badge/DOI/10.5281/zenodo.22115165.svg)](https://doi.org/10.5281/zenodo.22115165)
[![License: MIT](https://img.shields.io/badge/License-MIT-blue.svg)](LICENSE)

**Hierarchical Admixture & PCA Stability Lab** — a browser-based tool for exploring continent → region → population genetic signals from consumer raw DNA files (23andMe, AncestryDNA, MyHeritage, and VCF-style text).

> **Important:** results are model contributions under the current reference panel, not genealogical ancestry percentages, medical findings, or forensic conclusions.

## Editions

### Browser edition

- Open `index.html` in a modern browser, or use the hosted version if available.
- Load your own raw DNA file locally.
- Processing is designed to run on your device; review the app's privacy notes before use.

### Windows desktop edition

A Windows desktop wrapper built with Electron is available in [`desktop/`](desktop/).

- **Installer:** check the [GitHub Releases page](https://github.com/DavidH789/HelixMap-JS/releases). A downloadable installer must be attached to a release before this link provides a direct download.
- **Source and build instructions:** [`desktop/README.md`](desktop/README.md).
- **Current desktop package version:** 2.0.0.

The desktop edition packages the app for Windows. It does not turn the tool into a clinical or forensic product.

## Features

- Hierarchical admixture modelling: continents → regions → populations.
- Frequency quality weighting for reference data.
- PCA and stability diagnostics.
- Validation and model-comparison tools.
- Client-side processing design; any optional local caching is controlled by the app/browser.

## Quick start

1. Open `index.html` in Chrome, Firefox, or another modern browser.
2. Load a supported raw DNA text/CSV/ZIP file.
3. Review the in-app quality indicators and limitations before interpreting results.

No account or server is required for the browser workflow. Avoid uploading personal genetic data to public repositories, issues, or discussions.

## Interpretation limits

| Suitable for | Not suitable for |
| --- | --- |
| Exploratory genetic-signal visualisation | Clinical diagnosis or treatment decisions |
| Learning about PCA and reference-panel models | Forensic identification |
| Comparing model outputs with their stated limitations | Definitive claims of national or ethnic identity |

Country-level populations can be genetically close, and weak country-level estimates should be treated cautiously. Reference-panel coverage and data quality affect results.

## Privacy

- Treat raw genotypes and personal DNA reports as highly sensitive information.
- Do not commit personal DNA files, API keys, access tokens, or private test results to this repository.
- Check the app's own privacy and caching controls before processing your data.

## Citation

If you use HelixMap-JS in coursework, research, or a portfolio, cite:

> David (@DavidH789). *HelixMap-JS: Hierarchical Admixture & PCA Stability Lab*. Version 19.0. https://github.com/DavidH789/HelixMap-JS

## License and third-party data

The project code is released under the MIT License; see [`LICENSE`](LICENSE). Reference allele frequencies and embedded 1000 Genomes/NYGC-derived materials remain subject to their original terms and the relevant cited sources. This repository does not claim ownership of those third-party data.

## Author

**David** — [@DavidH789](https://github.com/DavidH789). Issues and pull requests are welcome.

Related project: [HelixOne](https://github.com/DavidH789/HelixOne).

## Roadmap

- [ ] Further separate the model engine from the UI.
- [ ] Export results to JSON/CSV.
- [ ] Improve documentation and reproducibility notes.
- [ ] Review offline support and browser storage controls.
