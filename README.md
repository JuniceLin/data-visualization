# Guided Alignment Evidence Explorer

A direct interaction redesign of DKMap's overview-to-detail workflow. The page keeps DKMap's core domain—multimodal projection and text–image alignment—while adding the entry summary, manual retrieval, and exploration guidance requested in DKMap's supplementary user study.

## Live demo

https://junicelin.github.io/data-visualization/

## Evidence layers

### 1. DKMap alignment overview

- **Official source:** [HKUST-CIVAL/DKMap](https://github.com/HKUST-CIVAL/DKMap)
- **Prepared data folder:** [DKMap Pick-a-Pic files](https://drive.google.com/drive/folders/1mz79GBRaBDKIUhrkWj1-l_LUUKacQBey)
- **Position file:** `CLIPScore_MFM.npy`, shape `(623694, 2)`
- **Metric file:** `CLIPscore_all_train_score.npy`, shape `(623694,)`
- **Browser subset:** 2,500 systematic points selected at evenly spaced source-array indices
- **Visual encoding:** released 2D position plus CLIPScore color
- **Boundary:** the browser subset does not reproduce DKMap training, contour estimation, or the full zoom hierarchy.

The compact JSON records the original file names, official folder, retrieval date, source coverage, sampling rule, score range, and source-array index for every displayed point.

### 2. DKMap validation evidence

The MAE values come from Table 1 of the official supplementary material. The questionnaire averages come from Figure 4. DKMap's visualization comparison involved 20 users; six participated in the follow-up interface questionnaire.

### 3. Preference-record inspection

A separate fixed slice uses Pick-a-Pic v2 mirror test rows 0–39. Thirty-five rows have definite labels: Image A was selected 17 times and Image B 18 times. Five rows have no definite label. Twelve labeled examples were manually content-screened for classroom display.

This preference slice is not presented as the source of the DKMap alignment map. Preference, CLIPScore alignment, and objective image quality are kept separate.

## Original gap and redesign response

DKMap already provides projection, alignment mapping, dynamic zoom, keyword distributions, and instance inspection. Its supplementary study reports requests for:

1. an overview summary at entry;
2. manual keyword retrieval;
3. more meaningful exploration guidance.

The redesign adds a guided reading order, a visible low-score threshold, pan and zoom, point inspection, source coverage, official validation charts, searchable preference examples, and adjacent supported/not-supported claims.

## Reproducibility

Run `tmp/infovis-redesign/build_dkmap_overview.py` after downloading the two official `.npy` files to the paths documented in that script. It checks that the coordinate and score arrays have the same length and selects 2,500 evenly spaced indices. A peer can then compare the generated compact JSON with the published file.

For the preference layer, retrieve the same Hugging Face test slice, retain rows with `has_label = true`, and count `label_0 = 1` and `label_1 = 1`.

## Supported and prohibited claims

Supported: inspection of a disclosed sample of official prepared DKMap coordinates and CLIPScores; comparison of published DKMap MAE and questionnaire values; description of the fixed 40-row preference slice.

Not supported: full reproduction of DKMap; a best-model claim; population preference; objective image quality; fairness; educational impact; or video motion and temporal-coherence conclusions.

## Technical notes

The project uses static browser-compatible HTML, CSS, JavaScript, canvas, and JSON. It has no React, npm, backend, Python runtime, local-path, or environment-variable dependency at run time. It includes responsive layouts, keyboard-accessible controls, alt text, status/error states, and visible attribution.

## AI-use disclosure

Codex assisted with source inspection, data auditing, implementation, accessibility checks, and drafting. The student selected the paper, research gap, sampling boundary, visual hierarchy, interactions, claim safeguards, and final wording, and remains responsible for the submission.
