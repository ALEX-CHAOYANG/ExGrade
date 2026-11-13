# ExGrade

Graded cross-study evidence for the molecular effects of exercise, for every gene, tissue, exercise paradigm and molecular layer in public omics data.

ExGrade is the interactive query website of the dataset described in Li C. & Su Q., *Uniformly re-analysed public omics data and graded meta-analyses of exercise responses in humans and rodents* (bioRxiv preprint, https://doi.org/10.64898/2026.11.06.764830). The full data record is archived at Zenodo (https://doi.org/10.5281/zenodo.23642143). It re-analyses 1,037 exercise–control comparisons from 448 independent studies (GEO, PRIDE and Metabolomics Workbench; human, mouse and rat), pools each molecular feature by random-effects meta-analysis within tissue × paradigm × layer units, and grades it against pre-specified criteria.

## What the site shows

- **Look up a gene**: for any gene, protein, miRNA or metabolite measured in at least three independent studies, the direction of change (up, down, no change, no detectable change or conflicting), the evidence class (I–IV, inconsistent, no detectable effect), the pooled effect size (Hedges' g) with 95% confidence and prediction intervals, heterogeneity, and replication in two held-out consortium atlases (MoTrPAC rat, Maier et al. mouse).
- **Browse by grade**: for any tissue × paradigm × layer unit (pooled, or one species), the complete list of features graded class I–III, which can be filtered by class, direction, number of studies, prediction interval and replication in the held-out atlases, sorted by any column and copied as a table.
- **Evidence map**: the evidence status of every tissue × paradigm × layer combination that has been studied, with contributing studies and the strongest graded features.
- **Reporting checklist**: the ExGrade minimum reporting checklist for exercise omics, with current reporting rates in GEO.
- **Browse by species and organ**: body maps of human, mouse and rat; selecting an organ filters the results, and selecting a species shows the exploratory species-stratified grades.
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
| `data/g/NNN.json` | Every class I–III feature of analysis unit NNN, taken from the per-feature results (`data/g/index.json`: counts per unit) |
| `assets/` | Body maps and organ pictures; sources and licences in `assets/CREDITS.txt` |

## Running locally

The page loads its data with `fetch`, so it must be served over HTTP rather than opened as a file:

```bash
python3 -m http.server 8000
# then open http://localhost:8000
```

## Status

Version 1.0.1 (November 2026). All pooled (all-species) estimates and evidence classes are identical to version 1.0 of the Zenodo data record. In addition, the species and organ browser shows a post hoc species-stratified analysis (55 units with at least three studies of one species, graded with the same rules); these species-specific results are not part of the data record or the preprint and should be treated as exploratory.

Known limitations of the data are described in the Technical Validation and Usage Notes of the preprint (for example, two PRIDE projects from one study are counted as separate studies, and in the held-out validation several muscles from the same animals were pooled).

## Licence

- Website code (`index.html`): MIT licence.
- Data shown on the website: CC BY 4.0, as in the Zenodo data record. Metabolite effect sizes are derived from Metabolomics Workbench studies, several of which are distributed under CC BY-NC-ND 4.0; users should check the licence of the original study before reusing metabolite results.
- Artwork in `assets/`: see `assets/CREDITS.txt` (CC BY 4.0 and CC BY 3.0, with attribution).

## Citation

Li C. & Su Q. Uniformly re-analysed public omics data and graded meta-analyses of exercise responses in humans and rodents. bioRxiv (2026). https://doi.org/10.64898/2026.11.06.764830

Data record (version 1.0): Zenodo (2026). https://doi.org/10.5281/zenodo.23642143
