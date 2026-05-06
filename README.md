# Conserved Yeast Heat-Shock Response Analysis

Cross-species RNA-seq analysis investigating the conservation of heat-shock–induced transcriptional responses between yeast, mouse, and human cells through differential expression analysis, homology mapping, and Gene Ontology enrichment.

## Overview

This project explores how different eukaryotic organisms respond transcriptionally to heat stress and which biological mechanisms remain conserved across evolution.

The analysis combines:

- Differential gene expression analysis
- Cross-species homology mapping
- Functional enrichment analysis
- GO semantic similarity analysis
- Data visualization in R

Species analyzed:

- *Saccharomyces cerevisiae* (yeast)
- Human HeLa cells
- Human fibroblasts
- Mouse melanoma cells

The results show that core heat-shock mechanisms, particularly protein folding and translation-related processes, remain conserved across species, while substantial species-specific transcriptional differences are also present.

---

## Main Features

### Differential Expression Analysis

Two separate pipelines were used depending on dataset format.

#### DESeq2

Used for raw count RNA-seq datasets:

- Yeast
- HeLa cells

#### limma

Used for normalized expression datasets (FPKM):

- Human fibroblasts
- Mouse melanoma cells

Genes were filtered using adjusted p-values and log2 fold-change thresholds.

---

### Homology Mapping

Cross-species homologous genes were identified using:

- HomoloGene
- Entrez Gene IDs
- Organism-specific annotation databases

Mappings were performed between:

- Human ↔ Yeast
- Mouse ↔ Yeast

---

### Functional Enrichment

Gene Ontology Biological Process enrichment was performed using:

- `clusterProfiler`
- `GOSemSim`
- `igraph`
- `GO.db`

The analysis identifies:

- Conserved biological processes
- Species-specific stress responses
- Shared heat-shock pathways

Key conserved processes include:

- Protein folding
- Ribosome biogenesis
- tRNA modification
- RNA processing

---

## Example Results

### Differentially Expressed Genes

| Dataset | Differentially Expressed Genes |
|---|---:|
| HeLa | 5044 |
| Mouse | 3485 |
| Yeast | 2579 |
| Fibroblasts | 1130 |

### Homolog Mapping Results

| Comparison | Homolog Mappings |
|---|---:|
| HeLa ↔ Yeast | 55 |
| Fibroblast ↔ Yeast | 47 |
| Combined Human ↔ Yeast | 97 |
| Mouse ↔ Yeast | 121 |

---

## Technologies

### Language

- R

### Main Packages

- DESeq2
- limma
- clusterProfiler
- homologene
- GOSemSim
- igraph
- GO.db
- org.Hs.eg.db
- org.Mm.eg.db
- org.Sc.sgd.db

---

## Datasets

Public GEO datasets used in this project:

| Dataset | GEO Accession |
|---|---|
| HeLa heat shock | GSE247417 |
| Human fibroblasts | GSE100469 |
| Mouse melanoma | GSE133251 |

---

## Biological Interpretation

The results support the idea that the core heat-shock response is evolutionarily conserved across eukaryotes.

Conserved pathways mainly involve:

- Protein quality control
- Translation regulation
- Ribosome-associated processes

At the same time, mammalian cells display substantially more complex transcriptional regulation than yeast, particularly in RNA-processing-related pathways.

---

## Repository Status

This repository currently contains the analysis pipeline and project code used for the comparative heat-shock response study.
Additional cleanup, documentation, and workflow organization are still in progress.
