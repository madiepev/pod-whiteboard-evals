# POD Whiteboard Evaluations

This repository contains an inventory of Microsoft Learn Data and AI visuals and a proposed dataset for evaluating agents that generate instructional visuals, including whiteboards.

## Contents

| File or folder | Purpose |
|---|---|
| [`agent-specification.md`](./agent-specification.md) | Defines the whiteboard agent's purpose, users, journey, environment, dependencies, and open decisions. |
| [`visual-guidelines.md`](./visual-guidelines.md) | Defines color, typography, whiteboard-style, and accessibility guidance. |
| [`whiteboard-images.csv`](./whiteboard-images.csv) | Lists possible and confirmed existing whiteboard-style images with source and review metadata. |
| [`wwl-data-ai-visuals.html`](./wwl-data-ai-visuals-share/wwl-data-ai-visuals.html) | Browse all collected visuals with their source context and metadata. |
| [`wwl-data-ai-visuals-stats.html`](./wwl-data-ai-visuals-share/wwl-data-ai-visuals-stats.html) | View descriptive statistics for the visual inventory. |
| [`evaluation-dataset-coverage.md`](./wwl-data-ai-visuals-share/evaluation-dataset-coverage.md) | See how the statistics translate into representative test coverage. |
| [`suggested-test-input-prompts.html`](./wwl-data-ai-visuals-share/suggested-test-input-prompts.html) | Review 20 real test cases with copyable prompts and evaluator-only reference images. |
| [`wwl-data-ai-visuals.csv`](./wwl-data-ai-visuals-share/wwl-data-ai-visuals.csv) and [`wwl-data-ai-visuals.json`](./wwl-data-ai-visuals-share/wwl-data-ai-visuals.json) | Use the source inventory for further analysis. |
| [`images/`](./wwl-data-ai-visuals-share/images/) | Access the local reference visuals used by the HTML pages. |
| [`test-dataset-feedback.yml`](./.github/ISSUE_TEMPLATE/test-dataset-feedback.yml) | Defines the GitHub form for adding, removing, or changing a test prompt. |

## Clone and open

```bash
git clone https://github.com/madiepev/pod-whiteboard-evals.git
cd pod-whiteboard-evals
code .
```

## View the HTML pages

In VS Code, right-click an HTML file and select **Open With > Integrated Browser**.

Alternatively, right-click the file, select **Copy Path**, open **Integrated Browser** or **Simple Browser: Show** from the Command Palette, and paste the path. Prefix the absolute path with `file://` if a URL is required.

## How to use the repository

1. Use [`wwl-data-ai-visuals.html`](./wwl-data-ai-visuals-share/wwl-data-ai-visuals.html) to explore the existing visuals.
2. Use [`wwl-data-ai-visuals-stats.html`](./wwl-data-ai-visuals-share/wwl-data-ai-visuals-stats.html) to understand their distribution.
3. Read [`evaluation-dataset-coverage.md`](./wwl-data-ai-visuals-share/evaluation-dataset-coverage.md) to see how that distribution informs representative, challenge, and negative test coverage.
4. Review the 20 selected cases in [`suggested-test-input-prompts.html`](./wwl-data-ai-visuals-share/suggested-test-input-prompts.html). The set contains 16 representative cases, 3 challenge cases, and 1 routing or non-diagram case.

## Supporting context

Each inventory record can contain:

- `section_heading`: the local topic;
- `preceding_paragraph`: text introducing the visual;
- `following_paragraph`: text continuing or explaining it.

The preceding and following paragraphs form the **supporting context**. Their combined word count is used for context-length analysis. Test prompts normally use the heading and adjacent paragraphs; long-context cases can use a full subsection, while sparse cases intentionally retain limited information.

The reference image, alt text, filename, category, and evaluator annotations are not included in the agent input.

## Data source

The current inventory was extracted from the `wwl-data-ai` folder of the `learn-pr` repository. Future versions are expected to include other folders and repositories.

## Reference images and negative tests

A reference image shows what the source content currently uses. It does not mean the agent should reproduce that format or always create a whiteboard.

Depending on the content, the better behavior may be to recommend a screenshot, chart, table, preserved code output, formal architecture diagram, or request for more context. A high-level architecture may suit a whiteboard, while a detailed deployment, network, security, or migration architecture may require a more precise format.

## Give feedback

Please [submit test dataset feedback](https://github.com/madiepev/pod-whiteboard-evals/issues/new?template=test-dataset-feedback.yml) to suggest adding, removing, or changing a prompt. For an existing case, include its prompt number.
