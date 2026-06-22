---
inclusion: manual
---

# Mermaid Diagram Conversion

When converting screenshots or images into Mermaid diagrams, follow these rules:

## Line Breaks and Formatting

- Use `<br>` for line breaks inside node labels — never use `\n`
- Use `<b>` and `</b>` for bold text inside nodes — never use `**`
- Use `<i>` and `</i>` for italic text inside nodes
- Always wrap node labels in double quotes: `["label text"]`

## Quotes and Special Characters

- Avoid using `"` inside node labels. If needed, omit them or use single quotes
- Avoid curly braces `{}` inside labels as they conflict with Mermaid shape syntax
- For JSON-like content, simplify to key: value format without braces

## Diagram Structure

- Use `flowchart LR` for left-to-right flows (most common for pipeline/process diagrams)
- Use `flowchart TD` for top-to-bottom flows (good for hierarchies)
- Use `subgraph` to group related nodes that share a visual boundary in the source image
- Use `direction TB` inside subgraphs when the internal flow differs from the main chart direction

## Node Shapes

- Rectangles `["text"]` for standard boxes
- Rounded `("text")` for softer containers
- Stadium `(["text"])` for pill-shaped nodes
- Diamond `{"text"}` for decision points
- Parallelogram `[/"text"/]` for input/output

## Edge Labels

- Use `-->|label|` for labeled arrows
- Use `-->` for unlabeled connections
- Use `-.->` for dashed arrows (optional/conditional flows)
- Use `==>` for thick arrows (emphasis)

## Best Practices

- Keep node text concise — move detailed content to markdown text above/below the diagram
- Match the visual layout of the source image as closely as possible
- Preserve the logical groupings shown in the source
- Label arrows when the relationship isn't obvious from context
- Test that the diagram renders without errors before presenting it
