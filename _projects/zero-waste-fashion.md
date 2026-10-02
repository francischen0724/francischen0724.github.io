---
layout: page
title: ZeroWasteFashionAI
description: A sketch-to-garment prototype combining computer vision, multimodal understanding, and pattern-layout optimization.
img:
importance: 5
category: engineering
---

**Sustainable Fashion AI Design Studio**

I co-led a student project exploring an AI-assisted sketch-to-garment workflow. The prototype combines computer vision, multimodal language models, and geometric layout optimization to help designers turn sketches into editable assets and structured garment descriptions, then explore more efficient fabric use.

**Role:** Co-leader.<br>
**Dates:** January-May 2025.<br>
**Status:** Research and engineering prototype.

## The problem

A hand-drawn sketch communicates visual intent but does not directly supply the editable outlines, component descriptions, or pattern-placement information needed for later garment work. The project explores how separate AI and geometry tools can support these steps within a design workflow.

## My contribution

- Developed sketch preprocessing and vectorization using adaptive thresholding, contour detection, path simplification, and SVG generation.
- Integrated a multimodal workflow for garment-component recognition, prompt-driven JSON structuring, and tech-pack summaries, covering components such as hoods, sleeves, cuffs, and pockets.
- Implemented 2D pattern-placement strategies using binary-tree bin packing, NFP-inspired polygon placement, and hybrid refinement with rotation and collision checks.
- Built a prototype pattern-optimization interface and evaluated net fabric consumption, reusable scraps, and optimization runtime.

## Prototype scope

The sketch-processing stage produces editable digital assets; the multimodal stage structures design information; and the layout stage explores placement of 2D pattern pieces. These components support an experimental design workflow. Producing manufacturing-ready patterns would additionally require validated dimensions, seam allowances, material constraints, and fit checks.

Layout evaluation considered both fabric consumption and the usefulness of the remaining scraps: a tightly packed layout can still leave offcuts that are difficult to reuse.

## Demonstrated results

For the **10-piece bin-packing example** shown in the team presentation, the reported results are:

| Measure                         |  Reported result |
| ------------------------------- | ---------------: |
| Net fabric consumption          | 29.97% reduction |
| Reusable share of leftover area |  71.79% → 84.21% |
| Processing time                 |     5.41 seconds |

Net fabric consumption subtracts reusable offcuts from the layout area. The implementation estimates reusable offcuts as sufficiently large empty rectangles, so the metric captures both compact placement and recoverable material. These measurements describe the demonstrated prototype layout; they are not averages across a garment dataset or measurements from manufacturing.

## Exploratory extensions

The repository also includes an experimental Gym environment and Stable-Baselines3 PPO implementation for sequential pattern placement. CLO 3D integration, virtual fitting, and more robust recognition of complex sketches were identified as future directions. The reported layout results above belong to the bin-packing prototype.

**Focus:** Computer vision, multimodal understanding, structured outputs, geometric optimization, and prototype development.

**Stack:** Python, OpenCV, scikit-image, Shapely, SVG/PDF generation; Gym and Stable-Baselines3 for the RL exploration.

[Repository (private; access required)](https://github.com/faraaz-usc/ZeroWasteFashionAI) · [All projects]({{ '/projects/' | relative_url }})
