title: Human Preference Lens for Generative Video
emoji: 📊
colorFrom: blue
colorTo: green
sdk: static
pinned: false
-------------

# Human Preference Lens for Generative Video

An accessible, responsive interactive visualization of aggregate human-preference comparisons between five text-to-video model labels.

## Data

The visualization uses aggregate statistics computed from verified fields in [Rapidata/text-2-video-human-preferences](https://huggingface.co/datasets/Rapidata/text-2-video-human-preferences).

- Publisher: Rapidata
- License: Apache-2.0
- Dataset update date: 2025-02-03
- Dataset commit: `b66676ff76ec68d14574f827a371563b75961b08`
- Coverage: 2,573 pairwise rows, 79 unique English prompts, and five model labels

The embedded values are derived aggregates, not simulated source records. Missing scores are excluded from the corresponding aggregate and are never treated as zero.

## Interactions

- Select one of ten model pairs.
- Compare prompt match, visual coherence, or aesthetic preference.
- Adjust the close-call threshold from 5 to 20 percentage points.
- Select any comparison-matrix row by mouse, touch, or keyboard to inspect it.

## Limitations

The dataset contains only 79 English prompts and five model labels from 2024–25. Human judgments are subjective, pair counts are uneven, some scores are missing, and participant recruitment and weighting details are limited. The visualization does not establish a universal model ranking.

## Static Space

The project is a self-contained static site. It does not require React compilation, npm, Python, a backend, local paths, environment variables, or non-HTTPS resources.
