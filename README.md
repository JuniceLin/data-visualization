# Guided Alignment Explorer

An interactive redesign of the **overview and keyword-exploration workflow** in DKMap. The redesign does not claim that text-to-image and text-to-video are equivalent. It transfers an interaction question from my earlier generative-video project—how can users inspect model evidence—into the image domain studied by DKMap.

## Live demo

GitHub Pages: https://junicelin.github.io/data-visualization/

## Design gap and response

DKMap's supplementary study reports requests for a clearer overview summary, manual keyword retrieval, and more meaningful keyword guidance. This prototype adds:

1. a guided four-step entry path;
2. a plain-language, evidence-first summary;
3. manual prompt keyword search and model/outcome filters;
4. record-level inspection of prompt, model, human label, date, and source row;
5. visible data boundaries and field definitions.

## Data contract

- **Purpose:** help newcomers inspect relationships among text prompts, generated image pairs, model labels, and recorded human choices.
- **Source:** [Pick-a-Pic v2 Hugging Face mirror](https://huggingface.co/datasets/liuhuohuo2/pick-a-pic-v2), with provenance linked to the [original PickScore project](https://github.com/yuvalkirstain/PickScore).
- **Exact query:** `test`, offset `0`, length `40`, via the Hugging Face datasets-server rows API.
- **Retrieved:** 2026-09-13.
- **Displayed records:** 12 classroom-safe labeled examples manually selected from that fixed slice.
- **Supported claim:** in the 35 definitely labeled rows of this slice, Image A was selected 17 times and Image B 18 times.
- **Prohibited inference:** the sample cannot rank models or represent the full dataset, its users, objective quality, or prompt alignment.
- **License:** the inspected mirror card did not state a license. Terms must be verified before reuse beyond this classroom demonstration.

## Reproducibility

The compact JSON file records the API query, retrieval date, fixed source-row identifiers, fields, transformations, and summary counts. A peer can retrieve the same slice, retain rows with `has_label = true`, and count `label_0 = 1` versus `label_1 = 1`. The gallery curation is separately declared so it is not confused with a statistical sample.

## Run locally

Serve this folder with any static HTTP server, then open `index.html`. Direct `file://` opening may block the JSON request; GitHub Pages is the intended public route. No React, npm, Python runtime, backend, or environment variables are required.

## References

- Y. Ye et al., “DKMap: Interactive Exploration of Vision-Language Alignment in Multimodal Embeddings via Dynamic Kernel Enhanced Projection,” IEEE VIS 2025 / TVCG 2026. DOI: https://doi.org/10.1109/TVCG.2025.3642641
- DKMap code: https://github.com/HKUST-CIVAL/DKMap
- Y. Kirstain et al., “Pick-a-Pic: An Open Dataset of User Preferences for Text-to-Image Generation,” NeurIPS 2023.

## AI-use disclosure

Codex assisted with data auditing, HTML/CSS/JavaScript implementation, accessibility checks, and documentation. The student selected the research gap, data boundary, visual emphasis, guided workflow, content-screening rule, and limitations, and remains responsible for every claim.
