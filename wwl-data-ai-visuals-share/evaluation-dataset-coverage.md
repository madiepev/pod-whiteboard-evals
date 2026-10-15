# Evaluation dataset coverage

This document explains how the proposed evaluation set represents the current `wwl-data-ai` visual inventory. The inventory is evidence about the source content, not a requirement to reproduce each existing image or format.

## Inventory baseline

The restored inventory contains 1,476 visual references from 198 modules.

| Existing visual category | Count | Share |
|---|---:|---:|
| Screenshot | 834 | 56.5% |
| Diagram | 503 | 34.1% |
| Others | 139 | 9.4% |

Screenshots and diagrams account for 90.6% of the inventory.

## Supporting-context coverage

Each expected prompt uses the section heading and the paragraphs immediately before and after the source image. Image metadata, the reference image, alt text, filename, category, and evaluator guidance are excluded from the agent input.

The combined adjacent context ranges from 5 to 341 words. Its distribution across the 1,476 inventory items translates to a 20-item evaluation set as follows:

| Combined context length | Inventory items | Inventory share | Expected in 20 items | Target occurrences |
|---|---:|---:|---:|---:|
| 5–24 words | 76 | 5.1% | 1.0 | 0 |
| 25–49 words | 323 | 21.9% | 4.4 | 5 |
| 50–74 words | 448 | 30.4% | 6.1 | 6 |
| 75–99 words | 317 | 21.5% | 4.3 | 5 |
| 100–149 words | 216 | 14.6% | 2.9 | 3 |
| 150–341 words | 96 | 6.5% | 1.3 | 1 |
| **Total** | **1,476** | **100.0%** | **20.0** | **20** |

The expected values are the inventory percentages multiplied by 20. Target occurrences use whole numbers and are balanced to keep the evaluation set at exactly 20 items. The final selection shifts one case from the shortest range to the 75–99-word range so that the complete numbered process for Prompt 12 is included.

The proposed cases include typical mid-length context plus deliberate sparse- and long-context challenges. A sparse prompt tests whether the agent requests clarification instead of inventing details. A long prompt tests whether it can identify and simplify the important relationships.

## Product and content-level coverage

The proposed cases span the following product or workload families:

| Product or workload family | Cases | Share |
|---|---:|---:|
| Microsoft Fabric | 5 | 25% |
| Microsoft Foundry and machine learning services | 5 | 25% |
| Cross-product data and AI fundamentals | 4 | 20% |
| Database services and SQL | 3 | 15% |
| Excel | 1 | 5% |
| GitHub and Visual Studio Code | 1 | 5% |
| Azure Databricks | 1 | 5% |
| **Total** | **20** | **100%** |

The cases also cover different purposes within the learning content:

| Content purpose | Description | Cases | Share |
|---|---|---:|---:|
| Introducing or explaining a concept | Explains a capability, process, or foundational idea | 8 | 40% |
| Implementing or using something | Guides a learner through a task, tool, or product experience | 10 | 50% |
| Designing or modeling something | Describes a data model, system structure, or architecture | 2 | 10% |
| **Total** |  | **20** | **100%** |

These groupings are inferred from the module, section heading, and supporting context because the source inventory does not contain product-family or content-purpose labels. They describe the proposed evaluation set rather than a statistically derived distribution of the full inventory.

## Target 20-case mix

The evaluation set should contain:

- **16 representative cases** that focus on diagram-based source material while retaining selected screenshots and other formats;
- **3 challenge cases** covering sparse context, long context, and architecture that requires precision; and
- **1 negative or routing case** that tests whether a whiteboard is appropriate or whether preserving the existing chart or output format is more useful.

Prompts are ordered by case role: representative cases (1–16), challenge cases (17–19), then the negative or routing case (20).

The full set should contain 15 diagram references, 4 screenshot references, and 1 chart reference for the negative or routing case. Prompt 11 uses the Fabric Warehouse append-versus-replace diagram instead of the notebook code/output example. Prompt 20 retains the chart-routing test. Diagram cases are the primary measure of whether the agent can produce clear and accurate whiteboards. Screenshot cases test how the agent handles content currently presented through a product interface. The evaluation should compare the usefulness of recommending a screenshot with creating a simplified rendering of the interface rather than assuming either approach is always correct.

## Reference-image policy

Reference images show what content developers have considered effective visuals for supporting their content. They are collapsed by default on the review page and are never part of the copied agent prompt.

Evaluators can compare a whiteboard output with its reference image as a sanity check. The reference is not the source of truth, and the output does not need to reproduce or closely resemble it.

## Known limitations

- The current inventory covers only the `wwl-data-ai` folder of `learn-pr`.
- Existing category labels describe the source visuals and can contain ambiguous or imperfect classifications.
- The set is intentionally small and is not statistically representative of every Microsoft Learn workload.
- Reference images must be restored under `images/` for local previews to render; prompt text and evaluator guidance remain usable without them.

## Final 20-item coverage tally

The same 20 items should satisfy each of the following coverage views. The counts across rows are overlapping dimensions and should not be added together.

| Coverage dimension | Representation in the 20-item set |
|---|---|
| Case role | 16 representative cases, 3 challenge cases, and 1 negative or routing case |
| Reference visual | 15 diagrams, 4 screenshots, and 1 chart (Other) |
| Supporting-context length | 5 with 25–49 words, 6 with 50–74, 5 with 75–99, 3 with 100–149, and 1 with 150–341 |
| Product or workload | 5 Microsoft Fabric, 5 Microsoft Foundry and machine learning, 4 cross-product data and AI fundamentals, 3 database and SQL, and 1 each for Excel, GitHub and Visual Studio Code, and Azure Databricks |
| Content purpose | 8 introducing or explaining a concept, 10 implementing or using something, and 2 designing or modeling something |
