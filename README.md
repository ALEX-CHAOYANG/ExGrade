# ExGrade

Graded cross-study evidence for the molecular effects of exercise, for every gene, tissue, exercise paradigm and molecular layer in public omics data.

ExGrade is the interactive resource accompanying the manuscript *Molecular effects of exercise training replicate mainly in skeletal muscle* (Li C. et al., in preparation). It re-analyses 1,037 exercise–control comparisons from 448 independent studies (GEO, PRIDE and Metabolomics Workbench; human, mouse and rat), pools each molecular feature by random-effects meta-analysis within tissue × paradigm × layer units, and grades it against pre-specified criteria.

## What the site shows

- **Look up a gene**: for any gene, protein, miRNA or metabolite measured in at least three independent studies, the direction of change (up, down, no change, no detectable change or conflicting), the evidence class (I–IV, inconsistent, no detectable effect), the pooled effect size (Hedges' g) with 95% confidence and prediction intervals, heterogeneity, and replication in two held-out consortium atlases (MoTrPAC rat, Maier et al. mouse).
- **Evidence map**: the evidence status of every tissue × paradigm × layer combination that has been studied, with contributing studies and the strongest graded features.
- **Reporting checklist**: the ExGrade minimum reporting checklist for exercise omics (Supplementary Note 5), with current reporting rates in GEO.
- **How grades work**: definitions of effects, direction calls, evidence classes and unit status.

The interface is available in English, 简体中文, 繁體中文, 日本語, 한국어, العربية, Español, Français, Deutsch, Português and Русский.

## Files

| Path | Content |
|---|---|
| `index.html` | The complete single-page application (no build step, no server code) |
| `data/units.json` | Analysis units, their studies, evidence status, status map and checklist |
| `data/index.json` | Search index of all features |
| `data/aliases.json` | Gene synonyms, mouse and rat symbols, Ensembl IDs |
| `data/i18n.json` | Interface text in 11 languages |
| `data/s/NNN.json` | Per-feature results, sharded so that each lookup loads one file |

## Running locally

The page loads its data with `fetch`, so it must be served over HTTP rather than opened as a file:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Status

Pre-publication version 1.0 (October 2026). Private until the manuscript is published; a licence and the public URL will be added then.

## Citation

Li C. et al. Molecular effects of exercise training replicate mainly in skeletal muscle. Manuscript in preparation (2026). ExGrade version 1.0.
