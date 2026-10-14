# Evaluation dataset coverage

This document explains how the proposed evaluation set represents the current `wwl-data-ai` visual inventory. The inventory is evidence about the source content, not a requirement to reproduce each existing image or format.

## Inventory baseline

The restored inventory contains 1,476 visual references from 198 modules.

| Existing visual category | Count | Share |
|---|---:|---:|
| Screenshot | 834 | 56.5% |
| Diagram | 503 | 34.1% |
| Other / unclear | 61 | 4.1% |
| Chart / graph | 23 | 1.6% |
| Photo / icon | 22 | 1.5% |
| Code / output | 11 | 0.7% |
| Animation | 9 | 0.6% |
| No alt text | 8 | 0.5% |
| Table | 3 | 0.2% |
| Mockup | 2 | 0.1% |

Screenshots and diagrams account for 90.6% of the inventory. The evaluation set therefore emphasizes both categories while retaining cases where a chart, code sample, screenshot, or formal architecture diagram is more appropriate than a whiteboard.

## Supporting-context coverage

Each normal prompt uses the section heading and the paragraphs immediately before and after the source image. Image metadata, the reference image, alt text, filename, category, and evaluator guidance are excluded from the agent input.

The combined adjacent context ranges from 5 to 341 words:

| Percentile | Words |
|---|---:|
| Minimum | 5 |
| 25th | 47 |
| Median | 67 |
| 75th | 94 |
| 90th | 128 |
| Maximum | 341 |

The proposed cases include typical mid-length context plus deliberate sparse- and long-context challenges. A sparse prompt tests whether the agent requests clarification instead of inventing details. A long prompt tests whether it can identify and simplify the important relationships.

## Proposed 20-case mix

The review page contains:

- **16 representative cases** that broadly reflect the screenshot-heavy inventory while covering diagrams, a chart, and code or output;
- **3 challenge cases** covering sparse context, long context, and architecture that requires precision; and
- **1 routing or non-diagram case** where the expected behavior is to recommend a screenshot or procedural capture rather than invent a whiteboard.

The representative subset contains nine screenshot references, five diagram references, one chart reference, and one code/output reference. This approximates the dominant inventory distribution without allowing screenshots to crowd out conceptual visual evaluation.

## Evaluation dimensions

Evaluate each response against the following dimensions:

1. **Grounding:** The response uses only the selected and surrounding content and does not invent services, steps, labels, values, or relationships.
2. **Instructional value:** The proposed visual helps a learner understand the concept faster than text alone.
3. **Format choice:** The agent chooses a whiteboard only when simplification is appropriate and recommends a screenshot, chart, table, preserved code/output, or formal diagram when precision matters.
4. **Technical accuracy:** Entities, sequence, grouping, direction, and dependencies remain correct.
5. **Visual clarity:** The result uses a clear hierarchy, concise labels, unambiguous connectors, and purposeful grouping.
6. **Style and accessibility:** The result follows `visual-guidelines.md`, including a white background, approved styling, readable text, sufficient contrast, and meaning that does not depend on color alone.
7. **Safe handling of uncertainty:** The agent requests more context when the prompt is too sparse to support a reliable visual.

## Reference-image policy

Reference images are evaluator-only evidence of what the source currently uses. They are collapsed by default on the review page and are never part of the copied agent prompt.

Do not score visual similarity as the primary success criterion. A response can be better than the reference by choosing a more suitable format, improving instructional clarity, or declining to create a misleading whiteboard.

## Known limitations

- The current inventory covers only the `wwl-data-ai` folder of `learn-pr`.
- Existing category labels describe the source visuals and can contain ambiguous or imperfect classifications.
- The set is intentionally small and is not statistically representative of every Microsoft Learn workload.
- Reference images must be restored under `images/` for local previews to render; prompt text and evaluator guidance remain usable without them.

