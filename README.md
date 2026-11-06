# RNA-seq-Analysis-of-Mouse-CD4-T-Cell-Differentiation-Naive-Th1-Th2-
# 🧬 RNA-seq Analysis of Mouse CD4+ T-Cell Differentiation (Naive, Th1 & Th2)

## 📌 Project Overview

This project focuses on the transcriptomic analysis of mouse CD4+ T-cell differentiation using bulk RNA sequencing (RNA-seq) data.

The primary objective is to identify differentially expressed genes (DEGs), investigate immune-related signaling pathways, and understand the molecular differences between naive CD4+ T cells and differentiated T helper cell subsets (Th1 and Th2).

The analysis uses publicly available RNA-seq data from the NCBI Gene Expression Omnibus (GEO).

**Dataset:** GSE123966  
**Organism:** *Mus musculus* (Mouse)  
**Technology:** Bulk RNA-seq  
**Cell Types:** Naive CD4+ T cells, Th1, Th2

> Note: The original case-study brief also mentions GSE60450. The final accession and sample selection should be verified against the actual count matrix and sample metadata before analysis.

---

## 🎯 Project Objectives

1. Download and preprocess publicly available RNA-seq count data.
2. Perform quality control and normalization of gene expression data.
3. Apply Principal Component Analysis (PCA) to investigate global transcriptomic variation.
4. Identify differentially expressed genes between:
   - Naive vs Th1
   - Naive vs Th2
5. Generate volcano plots to visualize significant upregulated and downregulated genes.
6. Generate heatmaps to visualize the expression patterns of top differentially expressed genes.
7. Perform functional enrichment and pathway analysis.
8. Investigate cytokine signaling and immune-related biological pathways.
9. Interpret the molecular mechanisms involved in CD4+ T-cell differentiation.

---

## 🧪 Biological Background

CD4+ T helper cells are essential components of the adaptive immune system. Depending on environmental cytokines and transcriptional signals, naive CD4+ T cells differentiate into specialized subsets.

### 1. Naive CD4+ T Cells
- Undifferentiated T helper cells.
- Have not yet acquired a specialized effector phenotype.
- Can differentiate into multiple T helper subsets.

### 2. Th1 Cells
- Important for cell-mediated immunity.
- Involved in defense against intracellular pathogens.
- Associated with IFN-γ production.
- Key transcription factor: **TBX21 (T-bet)**.

### 3. Th2 Cells
- Important for humoral and allergic immune responses.
- Involved in defense against helminth infections.
- Associated with IL-4, IL-5, and IL-13.
- Key transcription factor: **GATA3**.

---

## ⚙️ Technologies and Tools Used

| Technology | Purpose |
|---|---|
| Python | Data analysis and automation |
| GEO / NCBI | Public RNA-seq dataset acquisition |
| Pandas | Data manipulation |
| NumPy | Numerical computation |
| SciPy | Statistical analysis |
| Statsmodels | Multiple hypothesis testing correction |
| Scikit-learn | Principal Component Analysis |
| Matplotlib | Data visualization |
| Seaborn | Heatmaps and statistical plots |
| GSEApy | Gene set enrichment and pathway analysis |
| GEOparse | GEO dataset retrieval |

---

## 🔬 Project Workflow

### Step 1: Data Acquisition
- Retrieve publicly available RNA-seq data from NCBI GEO.
- Download raw gene expression count matrices.
- Obtain sample metadata and identify biological conditions.

### Step 2: Data Preprocessing
- Check missing values and sample consistency.
- Remove genes with very low expression.
- Perform appropriate normalization.
- Apply log transformation for visualization and exploratory analysis.

### Step 3: Exploratory Data Analysis (PCA)
Principal Component Analysis is used to reduce the dimensionality of the gene expression matrix and investigate similarities and differences among samples.

**Expected outcome:**
- Naive samples should show a distinct expression profile.
- Th1 and Th2 samples may separate due to their different differentiation programs.

### Step 4: Differential Gene Expression Analysis

Two primary comparisons are performed:

**Comparison 1: Naive vs Th1**
- Identify genes associated with Th1 differentiation.
- Investigate IFN-γ-related transcriptional responses.
- Examine transcription factors such as TBX21.

**Comparison 2: Naive vs Th2**
- Identify genes associated with Th2 differentiation.
- Investigate IL-4 and IL-13-related signaling.
- Examine transcription factors such as GATA3.

Statistical significance is assessed using:
- Adjusted p-value (FDR) < 0.05
- Absolute log2 Fold Change > 1

### Step 5: Volcano Plot Analysis
Volcano plots visualize differential expression using:
- X-axis: log2 Fold Change
- Y-axis: -log10(adjusted p-value)

Genes are categorized into:
- Upregulated genes
- Downregulated genes
- Non-significant genes

### Step 6: Heatmap Visualization
Heatmaps display the expression patterns of the top differentially expressed genes across samples.

They help identify:
- Th1-specific expression signatures.
- Th2-specific expression signatures.
- Genes associated with immune cell differentiation.

### Step 7: Pathway Enrichment Analysis
Functional enrichment analysis is performed to identify biological pathways associated with significant DEGs.

Areas of interest include:
- Cytokine-cytokine receptor interaction.
- JAK-STAT signaling.
- Th1 and Th2 cell differentiation.
- Interferon signaling.
- IL-4 and IL-13 signaling.
- Immune system activation.
- Inflammatory response.

---

## 📊 Expected Results and Visualizations

The project generates the following analytical outputs:

| Analysis | Output |
|---|---|
| PCA | Sample clustering plot |
| Differential Expression | DEG result tables |
| Volcano Plot | Upregulated and downregulated genes |
| Heatmap | Top DE gene expression patterns |
| Pathway Analysis | Enriched pathway tables and plots |

### Key Genes of Interest

| Th1-associated genes | Th2-associated genes |
|---|---|
| IFNG | IL4 |
| TBX21 | GATA3 |
| CXCR3 | IL5 |
| STAT1 | IL13 |
| IFNGR1 | CCR4 |

These genes are biological candidates to investigate, not assumed results. Their expression and statistical significance must be confirmed using the actual dataset.

---

## 📁 Repository Structure

```text
RNA-seq-CD4-T-Cell-Differentiation/
│
├── data/
│   ├── raw/
│   │   └── gene_counts.csv
│   │
│   └── processed/
│       └── normalized_counts.csv
│
├── notebooks/
│   └── RNAseq_Analysis.ipynb
│
├── scripts/
│   ├── data_preprocessing.py
│   ├── pca_analysis.py
│   ├── differential_expression.py
│   ├── volcano_plot.py
│   ├── heatmap.py
│   └── pathway_enrichment.py
│
├── results/
│   ├── PCA/
│   ├── Differential_Expression/
│   ├── Volcano_Plots/
│   ├── Heatmaps/
│   └── Pathway_Analysis/
│
├── figures/
│
├── requirements.txt
│
└── README.md
```

---

## 💻 Installation and Requirements

Clone the repository:

```bash
git clone https://github.com/YOUR_USERNAME/RNA-seq-CD4-T-Cell-Differentiation.git

cd RNA-seq-CD4-T-Cell-Differentiation
```

Install the required Python packages:

```bash
pip install pandas numpy scipy statsmodels
pip install scikit-learn matplotlib seaborn
pip install GEOparse gseapy
```

Or install all dependencies using:

```bash
pip install -r requirements.txt
```

---

## 🚀 Running the Project

1. Download the RNA-seq dataset from NCBI GEO.
2. Place the raw count matrix inside `data/raw/`.
3. Verify the sample metadata and experimental groups.
4. Run the preprocessing script.
5. Perform PCA and differential expression analysis.
6. Generate volcano plots and heatmaps.
7. Perform pathway enrichment analysis.
8. Review the results inside the `results/` directory.

---

## 🧠 Biological Questions Addressed

This project aims to answer the following research questions:

1. How does the gene expression profile of naive CD4+ T cells change during Th1 differentiation?
2. Which genes are significantly upregulated and downregulated during Th1 differentiation?
3. Which molecular signatures distinguish Th2 cells from naive CD4+ T cells?
4. What are the major cytokine signaling pathways associated with Th1 and Th2 differentiation?
5. How do transcriptional regulators such as TBX21 and GATA3 contribute to T helper cell specialization?

---

## 🔍 Scientific Significance

Understanding CD4+ T-cell differentiation provides insight into the molecular mechanisms regulating adaptive immunity.

This project demonstrates how computational transcriptomics can be used to:
- Identify immune cell-specific gene expression signatures.
- Investigate cytokine-mediated signaling mechanisms.
- Discover transcriptional regulators of immune differentiation.
- Explore molecular pathways associated with immune responses.
- Interpret biological changes through statistical and computational approaches.

---

## 📚 Data Source

NCBI Gene Expression Omnibus (GEO)

Dataset accession: GSE123966

https://www.ncbi.nlm.nih.gov/geo/

---

## 👨‍💻 Skills Demonstrated

- Bioinformatics
- Bulk RNA-seq data analysis
- Transcriptomics
- Gene expression analysis
- Statistical hypothesis testing
- Differential gene expression
- Principal Component Analysis (PCA)
- Data visualization
- Functional enrichment analysis
- Python programming
- Immunoinformatics
