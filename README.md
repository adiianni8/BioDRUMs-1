# BioDRUMs

**Getting started**
A Python pipeline to streamline mean Drug‑to‑Antibody Ratio (DAR) and biologics structural integrity (SI) analysis from high‑resolution mass spectrometry (HRMS) data
<img width="900" height="600" alt="Figure 1" src="https://github.com/user-attachments/assets/3f820de9-8756-4976-ac62-582c1bb6d4bc" />

**Overview**
BioDRUMs (Biologics Drug Ratio & Unified intact Mass analysis) is a Python pipeline with a graphical user interface (GUI) for automating:

**Mean drug‑to‑antibody ratio (DAR)** analysis of antibody-drug conjugates (ADCs) and other bioconjugates
**Structural integrity (SI)** analysis of unconjugated antibodies, bispecifics, and multispecific biologics
**Proteoform hypothesis generation** and assignment after intact MS deconvolution
**Quality control (QC)** on intact MS data (explained area %, isobaric species count)
It is designed to work on intact protein data from high‑resolution MS instruments and to standardize data processing across in vitro and in vivo studies (e.g. plasma stability, pharmacokinetics), including low‑volume small‑animal studies where replicate injections are often not feasible. It also works quite well for ADCs/biologics characterization in buffer, where high amount of sample is available.

If you use BioDRUMs in your work, please cite:

**Di Ianni et al., “BioDRUMs: a Python‑based pipeline to streamline mean drug‑to‑antibody ratio and biologics structural integrity analysis from high‑resolution mass spectrometry analyzers”, journal details to be added.**

**Features**

BioDRUMs provides:

**Automated proteoform hypothesis generation**

Combines antibody backbone masses, theoretical DAR ladder, linker–payload and degradation products, and (optional) glycoforms
Supports both glycosylated and deglycosylated intact proteins (glycan multiplier set to 2) or subunits(glycan multiplier set to 1).

**Unified DAR and SI analysis**

Mean DAR over time or concentration for ADCs/bioconjugates
Mean SI values for unconjugated biologics, where intact full‑domain species are scored SI = 1 and non‑intact species SI = 0

**Quality‑control metrics for intact MS experiments**

**Explained area %**: percentage of deconvoluted MS peaks that can be assigned to modeled species (typical threshold ≥ 75%)
**Isobaric species count** per DAR level or proteoform, to indicate assignment ambiguity (this is done on the whole set of generated DAR species, but you should look into your identified DAR species only)

**Flexible input compatibility**

Accepts table‑formatted deconvolution output from commercial and open‑access software (e.g., BioPharma Finder ReSpect™, UniDec, others), as long as the table includes:
a species mass / ID
**DAR value** for each species (when applicable)

**protein name**

**sum intensity**

Data filtering based on user‑tunable thresholds (default settings= 30 ppm mass accuracy, 4% relative abundance vs base peak)

**User‑friendly GUI**

No prior coding experience required
Dedicated windows for:
Proteoform mass calculation and hypothesis generation
DAR / SI analysis, QC metrics, and plotting

Installation
Requirements
Python ≥ 3.x
Standard scientific Python stack (e.g. pandas, numpy, matplotlib)
GUI library (e.g. tkinter or as specified in requirements.txt)
BioDRUMs operates on already deconvoluted intact MS data. You will also need:

A deconvolution software (e.g. BioPharma Finder 4.0 with ReSpect™, or other tools that export tabular deconvolution results)
The corresponding Excel template for BioDRUMs input (see below: Input templates)
