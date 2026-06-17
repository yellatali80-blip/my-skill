---
name: rebuild-editable-pptx
description: Recreate slide images, PPT screenshots, image-only PPT pages, or visual references as high-quality element-level editable PowerPoint PPTX files. Use when the user asks to restore, redraw, rebuild, replicate, or convert a slide image into an editable deck without using the whole original image as a background; especially for Chinese slides, tables, charts, icons, diagrams, infographics, and complex business or academic layouts.
---

# Rebuild Editable PPTX

## Core Rule

Rebuild the slide as editable PowerPoint content. Do not use the full source image as a slide background or full-page overlay. Decompose the image into text, shapes, lines, arrows, tables, charts, icons, illustrations, and decorative assets, then recreate each layer with the most editable suitable object.

## Workflow

1. Analyze every source image before building:
   - Record page aspect ratio, visual size, margins, grid, background, dominant colors, typography, hierarchy, and layer order.
   - Identify all elements and classify them as text, native shapes, lines/arrows, tables, charts, icons, illustrations, photos, or decorative assets.
   - Extract all text with OCR/vision and verify Chinese carefully.

2. Create the PPTX scaffold:
   - Set slide dimensions to match the source image aspect ratio.
   - Use one slide per source image unless the user requests otherwise.
   - Use Microsoft YaHei (`微软雅黑`) for all recreated text unless the user gives a different font requirement.

3. Rebuild editable fundamentals first:
   - Recreate all text as native PPT text boxes. Preserve content, line breaks, alignment, font size, weight, color, spacing, and hierarchy. Prevent乱码, overflow, clipping, overlap, and unintended wrapping.
   - Recreate simple color blocks, frames, dividers, line art, arrows, callouts, and geometric diagrams with native PowerPoint shapes. Remove extra shadows, glows, and effects unless they are visibly part of the source.
   - Recreate tables with native PPT tables when possible; otherwise use grouped editable shapes and text boxes.
   - Recreate charts with native PPT charts when feasible. If source data cannot be read exactly, estimate values from visual proportions and clearly note the uncertainty in slide notes or a small unobtrusive annotation.

4. Redraw non-native visual assets:
   - Redraw icons from scratch as native vector shapes, SVG, or transparent PNG assets. Do not crop icons from the source image.
   - Redraw complex diagrams, decorations, and illustrations as transparent-background assets when native shapes would be impractical.
   - Preserve transparent channels. Reject assets with white borders, watermarks, compression artifacts, wrong style, or garbled text.

5. Assemble precisely:
   - Match the source layout one-to-one in position, size, color, angle, spacing, alignment, and z-order.
   - Group logically related elements without flattening editable text.
   - Keep repeated styles consistent across slides.

6. Verify and iterate:
   - Render/export the PPTX to images or PDF and compare against the source.
   - Fix text errors, missing elements, color drift, misalignment, wrong icon proportions, table/chart mismatch, clipped objects, overlap, and transparency problems.
   - Repeat until the deck is visually faithful and remains editable.

## Element Rules

- Text: always native text boxes; use `微软雅黑`; keep Chinese clear and accurate.
- Shapes: use native PPT shapes for rectangles, capsules, lines, arrows, frames, connectors, badges, and simple diagrams.
- Tables: use native table objects or editable shape groups; do not leave table text embedded in images.
- Charts: prefer native chart objects; estimate unreadable data only when necessary and mark the estimate.
- Icons: redraw or regenerate with transparent backgrounds; never crop source icons directly.
- Illustrations: redraw as transparent assets while matching the original style.
- Backgrounds: recreate with native fills, gradients, patterns, or separately redrawn decorative assets; never place the original image as a full-slide background.

## Final Checklist

Before delivery, confirm:

- Slide size matches the source image ratio.
- Text content is complete, accurate, editable, and uses `微软雅黑`.
- No text is garbled, clipped, overflowing, or hidden.
- Shapes, arrows, frames, tables, charts, icons, and illustrations are recreated as editable or separately redrawn elements.
- Colors, spacing, alignment, hierarchy, and layer order match the source.
- Transparent assets have clean alpha channels with no white edge, watermark, or unwanted background.
- Any estimated chart/table data is clearly noted.
- The final `.pptx` opens correctly and remains editable.
