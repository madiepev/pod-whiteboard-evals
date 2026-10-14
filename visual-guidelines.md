# Visual Guidelines

Use these guidelines for generated Microsoft Learn whiteboards and other instructional visuals.

## When to create art

Use visual art to simplify complex subjects, especially in introductory content. Conceptual art and architecture diagrams should help readers understand the content faster, not repeat the text.

Art occupies screen space, so use it only when it adds instructional value.

## Microsoft Learn standards

- Use a two-dimensional design.
- Do not add decorative borders.
- Use the correct dimensions for the content and publishing location.
- Use current Microsoft icon, font, and color styles.
- Ensure the visual is legal to use and accessible.
- Use a white background.
- Use Segoe and no more than two font sizes.

Source: [Create conceptual art for Microsoft Learn](https://review.learn.microsoft.com/en-us/help/contribute/contribute-how-to-create-conceptual-art?branch=main)

## Security

- Do not include sensitive, personal, confidential, or secret data in the visual or prompt.
- Use fictional and non-sensitive sample names, values, endpoints, and identifiers.
- Ensure any depicted samples or architectures follow current security practices.

Sources: [Writing content securely](https://aka.ms/security-guidance-landing-page) and [Samples lifecycle](https://review.learn.microsoft.com/en-us/help/contribute/samples/concepts/sample-lifecycle)

## File type and background

- Prefer **SVG** for conceptual whiteboards because it scales without losing clarity.
- Use **PNG** when SVG is not suitable.
- Consider that SVG currently does not render in PDF output.
- If an SVG contains text, follow the publishing workflow for converting that text to SVG paths when required.
- Use a white background for conceptual art that contains text.
- Avoid transparent backgrounds behind text because the content can become unreadable in dark themes.
- Transparency is acceptable for branded icons and other non-text artwork when it works in every supported theme.
- Do not add a border around the conceptual image.

For an SVG, a white background can be declared on the root element:

```xml
<svg xmlns="http://www.w3.org/2000/svg" style="background-color: white">
```

## Color palette

- Use the approved Microsoft Learn theme palette.
- Use **Accent 1** and **Accent 2** as the main accent colors.
- Use **Accent 3** and **Accent 4** when additional colors are needed.
- Use **Accent 5** and **Accent 6** sparingly.
- Avoid using too many colors in one visual.
- Use the approved Microsoft Learn light and dark custom colors.
- Limit automatically generated tints and tones.
- Do not use PowerPoint standard colors.

Obtain exact color values from the approved Microsoft Learn template. Do not sample production colors from screenshots or recreate them approximately.

## Application

- Use color to communicate grouping, emphasis, status, or flow.
- Apply the same color consistently to the same concept.
- Maintain sufficient contrast between text, lines, shapes, and the background.
- Do not rely on color alone to communicate meaning; also use labels, shape, position, or line style.
- Prefer a small, purposeful palette over decorative color.

## Typography

- Use approved Microsoft Learn fonts when they are available in the output format.
- Keep labels short and readable.
- Use a clear hierarchy for titles, group labels, and supporting text.
- Avoid shrinking text to fit excessive content; simplify the visual instead.

## Whiteboard style

- Prioritize instructional clarity over decoration.
- Use simple shapes, connectors, labels, and grouping.
- Keep flows and relationships easy to follow.
- Preserve technical accuracy when simplifying.
- Use a formal diagram format instead when a whiteboard would remove important architectural, deployment, security, or network detail.

## Accessibility

- Provide meaningful alt text that communicates the purpose of the final visual.
- Provide a long description when the image is too complex to explain fully in alt text.
- Do not add alt text to purely decorative icons.
- Ensure text remains legible at the size used in Microsoft Learn.
- Use high-contrast colors and maintain a contrast ratio of at least **4.5:1** for text and essential visual elements.
- Validate text and visual-element contrast with the Color Contrast Analyzer or an equivalent accessibility tool.
- Avoid overlapping elements and ambiguous connectors.
- Use directional arrows only when direction is meaningful.
- Do not use color as the only way to communicate status or category.
- Pair colors with distinct shapes, labels, icons, patterns, or line styles.
- Include a legend when shapes or colors represent statuses or categories.
- Check that the visual remains understandable for people with color-vision deficiencies and when viewed without color.

Source: [Accessibility guidelines for multimedia](https://review.learn.microsoft.com/en-us/help/contribute/contribute-accessibility-multimedia)

## Theme testing

Test every whiteboard in all three Microsoft Learn themes:

- **Light**
- **Dark**
- **High contrast**

Confirm that the background, text, connectors, icons, and status indicators remain readable in each theme.
