# Methods (summary)

HelixMap-JS estimates **model contributions** of reference populations to a single consumer genotype vector. It does **not** output certified genealogical ancestry fractions.

## Input

- Raw genotype files: 23andMe, AncestryDNA, MyHeritage (`.txt` / `.csv` / `.zip`).
- Matched SNPs against an embedded reference panel (allele frequencies + quality tags).

## Hierarchical EM

1. Match user genotypes to the panel; convert to dosage relative to the derived allele.
2. **Continent-level** EM with soft Bayesian priors (e.g. down-weight spurious Oceania).
3. **Region-level** EM within continents (especially EUR: NW_EUR, E_EUR, S_EUR, SE_EUR, JEW).
4. **Population-level** EM only inside regions with strong signal.
5. SNP weights combine Rosenberg-style informativeness (computed on REAL anchors) and per-frequency **quality** (REAL > LIT > BLEND > PROXY).

Unresolved country clusters (no dominant population inside a region) are reported as clusters rather than tiny noisy country %.

## PCA

- Built on **allele-frequency vectors only** (labels never enter the Gram matrix).
- LD pruning (prefer empirical *r²* from embedded 1000G dosages when available) + column weights √*Iₙ*.
- Top-3 PCs; Procrustes alignment for hold-out / leave-one-population-out stability.
- Optional user stability: leave-chromosome / AIT / pigment blocks when DNA is loaded.

## Validation

- **Self-simulation** (HWE draws from reference frequencies): upper bound on recovery of anchors.
- **Real 1000G** (embedded NYGC 30× subset): continent / region / top-1 / top-3 accuracy and confusion matrices.
- **Hold-out** and **LOO**: stability when SNPs or populations are removed; UI refuses to invent scores without fit/rebuild APIs where applicable.

## Privacy

All inference runs in the browser. Optional DNA persistence uses IndexedDB on the user’s device only, with an explicit delete control.
