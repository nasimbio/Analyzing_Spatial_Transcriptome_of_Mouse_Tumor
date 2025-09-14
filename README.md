# Analyzing Spatial Transcriptome of Mouse Tumor(colon cancer metastases in liver)

This project analyzes CosMx spatial transcriptomics data from two slides, each containing two distinct tissue regions, totaling **three tumor** and **one control** sample. The analysis integrates spatial gene expression with cell type annotation via reference single-cell RNA-seq data, aiming to explore spatial clustering and cell type composition across conditions.

---

## 📘 Project Overview

Spatial transcriptomic profiles were generated using **Nanostring CosMx SMI** technology. Two slides were analyzed, each containing multiple tissue sections. A reference scRNA-seq dataset with annotated cell types was used to transfer labels to spatial cells using **Seurat’s `MapQuery()`** method. The focus was to evaluate how cell types are distributed in tumor versus control and identify key expression patterns across spatial regions.

---

## 📊 Analysis Tasks

### **Task 1: Preprocessing and Spatial Clustering**
- Load Nanostring CosMx outputs and generate a Seurat object for each slide
- Add metadata identifying each tissue section (e.g., tumor/control, slide ID)
- Merge both slide Seurat objects into a single dataset
- Perform quality control filtering
- Normalize and scale the data
- Run dimensionality reduction and clustering
- Identify marker genes for each spatial cluster

### **Task 2: Cell Type Annotation Using Single Cell Reference**
- Prepare an annotated single-cell reference object
- Identify **common genes** between reference and spatial query datasets
- Standard Seurat preprocessing (normalization, PCA)
- Use `FindTransferAnchors()` based on common genes
- Apply `MapQuery()` to transfer cell type labels from reference to CosMx spatial cells
- Visualize predicted labels and spatial distributions

**Note:** The spatial query dataset was already processed and normalized. `MapQuery()` enables mapping without needing to downsample cells or match dataset sizes, as long as the shared gene set is consistent.

---

# 💡 Notes

- Raw data is not publicly available due to client ownership and confidentiality.
- Some example outputs plots are organized by task in the `output/` folder.
- This project is designed for both reproducibility and clarity.

---

## 📬 Contact

*Author:* Nasim Rahmatpour 
*Email:* nasimrahmatpour1@gmail.com 
*GitHub:* (https://github.com/nasimbio)
