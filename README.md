# bipolar-lithium-pharmacogenomics
Integrative pharmacogenomics analysis of lithium response in bipolar disorder, contextualizing GWAS loci with Ensembl gene annotations and GTEx brain expression data using a reproducible R Markdown workflow.

# Genetic and Transcriptomic Context of Lithium Response in Bipolar Disorder

## Overview

This project examines the genetic and transcriptomic context of lithium treatment response in bipolar disorder using publicly available human genomics reference data and curated genome-wide association study (GWAS) results. The goal is not to build a predictive clinical model, but to contextualize reported lithium response loci within biologically relevant genes, pathways, and brain expression patterns.

Lithium remains one of the most effective treatments for bipolar disorder, yet patient response is highly heterogeneous. Understanding the biological context of genetic associations may help prioritize candidate genes and pathways for downstream functional and translational studies.

---

## Scientific Question

**Are genetic loci associated with lithium treatment response in bipolar disorder linked to genes with plausible relevance in human brain tissue?**

---

## Data Sources

This analysis integrates multiple publicly available human genomics resources:

- **Lithium response GWAS**
  - Curated loci from the Consortium on Lithium Genetics (ConLiGen)
  - Hou et al., 2016 (European ancestry samples)
  - Continuous (Alda scale–derived) and dichotomous response phenotypes

- **Human reference genome and gene annotations**
  - Ensembl GRCh38 reference genome
  - Ensembl release 115 gene annotations (GTF)

- **Tissue expression reference**
  - GTEx v10 median gene-level TPM values
  - Brain tissues only (bulk RNA-seq)

- **Pathway annotations**
  - MSigDB Hallmark gene sets (human gene symbols)

Due to data-sharing restrictions, individual-level genotype and phenotype data from ConLiGen and the Psychiatric Genomics Consortium (PGC) are not included.

---

## Methods Summary

1. Genome-wide significant and suggestive lithium response loci were curated from published GWAS results.
2. SNPs were mapped to nearby genes using Ensembl gene annotations.
3. Gene-level biological context was added using GTEx v10 median expression values across human brain tissues.
4. Genes were categorized as protein-coding or noncoding/regulatory for interpretability.
5. Results were summarized in a reproducible R Markdown workflow with a single illustrative figure.

This workflow mirrors post-GWAS interpretation strategies commonly used in academic and pharmaceutical research (e.g., MAGMA, FUMA), implemented explicitly for transparency.

---

## Key Results

- Lithium response loci map to a heterogeneous set of genomic features, including protein-coding genes, noncoding transcripts, and intergenic regions.
- A subset of loci map to protein-coding genes with robust expression in human brain tissue, such as **LHFPL3**, supporting biological plausibility in a central nervous system context.
- Other loci map to noncoding or lowly expressed regions, consistent with regulatory mechanisms commonly observed in psychiatric genetics.

**Figure 1.** Mean brain expression of lithium response–associated genes using GTEx v10 median TPM values. Protein-coding genes show higher expression in bulk brain tissue compared with noncoding or regulatory loci.

---

## Discussion and Limitations

This analysis is based on summary-level GWAS results rather than individual-level genotype and phenotype data. As a result, fine-mapping, conditional analyses, polygenic modeling, and patient-level prediction were outside the scope of this project. Access to individual-level data would enable deeper investigation of ancestry-specific effects, gene–gene interactions, and integration with longitudinal clinical outcomes.

SNP-to-gene mapping was based on reported annotations and genomic proximity and does not capture long-range regulatory interactions. GTEx expression values represent bulk tissue averages and may not reflect cell-type–specific or disease-state–specific expression patterns relevant to lithium response.

Despite these limitations, this project demonstrates a reproducible framework for contextualizing psychiatric pharmacogenomic findings using publicly available human reference data and provides a foundation for deeper analyses when individual-level clinical and molecular data are available.

---

## Reproducibility

All analyses were performed in R using an R Markdown workflow. The repository is structured to clearly separate raw reference data, processed results, and analysis code.

Large reference files (e.g., genome FASTA, GTEx matrices) are not included in the repository and must be downloaded separately from their original sources.

---

## Intended Audience

This project is intended for:
- Academic researchers in psychiatric genetics
- Pharmaceutical scientists interested in pharmacogenomics
- Data scientists working with human genomics and transcriptomics

It is designed to demonstrate analytical rigor, biological interpretation, and readiness to work with sensitive clinical and genetic datasets in controlled research environments.

---

## References

- Hou et al., 2016. *Genome-wide association study of lithium response in bipolar disorder.*  
- GTEx Consortium, v10.  
- Ensembl Genome Browser, GRCh38.  
- Molecular Signatures Database (MSigDB).
