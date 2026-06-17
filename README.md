# Whole-Slide Histology Registration Portfolio

Public-facing portfolio for my transition from medical biotechnology into computational pathology, biomedical image analysis, and biomedical visualization.

This repository does **not** publish MSc thesis data, patient-level material, private laboratory files, unpublished figures, dataset identifiers, supervisor-specific implementation details, or the original thesis code. Instead, it documents the **computational reasoning, workflow structure, and quality-control concepts** behind my current research direction using only non-sensitive descriptions and future synthetic/public examples.

## Current Research Direction

I am an MSc Medical Biotechnology student at the University of Padua, working toward computational biomedical research. My current thesis direction is connected to whole-slide histology image analysis, serial tissue-section alignment, image registration, deformation-aware workflow design, and preparation of histology data for later tissue reconstruction and visualization.

My background is biology-first: molecular biology, cancer biology, genomics, epigenetics, protein engineering, pharmacogenomics, PCR methodology, and translational medicine. I am using that biological background to move into computational pathology and image-based biomedical research.

## Why This Matters

Serial histology sections are often not naturally aligned. Tissue cutting, mounting, staining, scanning, resolution differences, and deformation can create shifts, rotations, scale differences, local distortions, missing tissue, or edge/crop artifacts.

For downstream computational pathology or 3D tissue reconstruction, simple visual overlap is not enough. A useful registration workflow should also consider internal tissue features, local morphology, tissue masks, no-data regions, cropping risk, and deformation safety.

## Workflow Concept

The public version of the workflow can be summarized as:

```text
Whole-slide input
→ working-image preparation
→ tissue masking
→ baseline / candidate registration methods
→ feature-based affine alignment
→ optional non-rigid refinement
→ tissue-overlap and artifact checks
→ feature-level quality control
→ deformation-aware result selection
→ high-resolution export for downstream visualization
```

The repository is intended to show how I think about a controlled registration pipeline rather than to release private thesis material.

## Technical Components

Main concepts and tools I am learning or using around this work:

- Python-based workflow organization
- OpenSlide-style whole-slide image handling
- OpenCV image processing
- SimpleITK / medical-image registration concepts
- NumPy, SciPy, Pillow, and reproducible preprocessing
- Tissue-mask generation and overlap evaluation
- Feature-based matching concepts such as SIFT and RANSAC
- Affine registration and cautious non-rigid refinement
- Dice and IoU as tissue-mask overlap metrics
- Crop, edge, blank-area, and no-data checks
- Sampling-field / coordinate-mapping concepts
- QuPath, Fiji/ImageJ, and 3D Slicer as related visualization environments

## Quality-Control Logic

A key lesson from this work is that tissue-boundary overlap does not necessarily prove good histological alignment. Two sections may appear globally aligned while nuclei, ducts, stromal structures, tumor regions, or local texture remain mismatched.

For that reason, the workflow direction emphasizes multiple layers of QC:

- tissue-mask overlap for global alignment sanity checks,
- internal feature consistency for local alignment assessment,
- crop and edge checks to avoid losing tissue,
- no-data checks to detect blank or invalid output regions,
- conservative handling of non-rigid deformation,
- visual inspection and interpretable overlays before trusting a result.

## What This Repository Can Publicly Show

This portfolio can safely include:

- general workflow diagrams,
- synthetic registration examples,
- non-sensitive toy demonstrations,
- public-data examples only when licensing is clear,
- conceptual explanations of registration and QC,
- documentation of tools and learning direction.

This portfolio will not include:

- raw SVS files,
- private JPEG references,
- real thesis outputs,
- patient/sample identifiers,
- exact local file paths,
- unpublished lab figures,
- private implementation details,
- code copied from the thesis pipeline without approval.

## Planned Public Demo

The next safe addition will be a small synthetic demo showing the registration logic without using real thesis images. The goal is to demonstrate the idea of:

1. creating a reference image,
2. creating a transformed moving image,
3. estimating alignment,
4. warping the moving image back,
5. reporting simple QC metrics,
6. visualizing before/after overlays.

This will make the repository useful for PhD applications while keeping the thesis material confidential.

## Research Interests

- Computational pathology and digital pathology
- Whole-slide image analysis
- Biomedical image registration
- Histology image alignment
- Spatial biology and image-based biomedical research
- 3D tissue reconstruction and biomedical visualization
- Cancer bioinformatics and medical AI
- Explainable biomedical AI workflows

## Confidentiality Statement

This repository is intentionally designed as a **methodology portfolio**, not a data release. More detailed thesis material can only be shared privately and only when appropriate, with supervisor/lab approval.
