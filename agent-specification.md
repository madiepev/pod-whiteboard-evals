# Whiteboard Agent Specification

## Purpose

Generate a whiteboard for a selected section of Microsoft Learn skilling content. A content developer selects a section of a unit, and the skill creates a visual explanation of that section.

The output format and storage location still need to be confirmed. Options include a raster image such as PNG, SVG, or a diagram format such as Mermaid, stored with the module's media assets.

## Intended users

- **Microsoft Learn content developers:** select the section, run the skill, and review the result.
- **Learners:** see the approved whiteboard in the published unit.

## User job to be done

As a content developer, I want to select a section of a unit and get a whiteboard that explains it, so that learners understand the concept faster without me designing the visual by hand.

## User journey

1. The content developer works in VS Code in their fork of the `learn-pr` repository.
2. They select a section of a unit and run the whiteboard skill.
3. The skill generates a whiteboard from the selected content.
4. The developer reviews, edits, or regenerates the whiteboard and adds the approved result to the unit.

## Evaluation unit

One evaluation unit consists of:

- one selected section of skilling content; and
- the whiteboard generated for that section.

## Environment

- VS Code
- The content developer's fork of the `learn-pr` repository
- Expected runtime: GitHub Copilot in VS Code

The final skill packaging and invocation method still need to be confirmed.

## Inputs and dependencies

- The selected section
- Relevant surrounding unit and module content
- Authenticated access to a Foundry-deployed text-to-image model, such as `gpt-image-2`, `gpt-image-2.5`, `gpt-image-2.5-flare`, or `MAI-Image-2.6`
- Authentication that complies with Microsoft and MCAPS policies, using Microsoft Entra ID or approved key-based authentication
- [`visual-guidelines.md`](./visual-guidelines.md) for consistent Microsoft Learn colors, fonts, and visual treatment

## Output expectations

- The result explains the selected section visually.
- The result remains grounded in the selected and surrounding content.
- The developer can review and regenerate the result before publication.
- The skill should recommend another format or request more context when a whiteboard would be misleading.

## Open decisions

- Whiteboard output format
- Media filename and storage location in the module
- Final Copilot skill packaging and invocation
- Approved model deployment and authentication method
- Microsoft Learn whiteboard style specification

## Evaluation data provenance

The current visual inventory was extracted from the `wwl-data-ai` folder of the `learn-pr` repository. Future dataset versions are expected to include content from other folders in `learn-pr` and from other repositories.
