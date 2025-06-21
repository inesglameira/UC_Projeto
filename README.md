This repository contains the bioinformatics pipeline and supporting files for the project:

## **"Identification of new breast cancer-related biomarkers via integrated bioinformatics analysis and experimental validation"**  
by *Inês Lameira, University of Minho*

### 🧬 Overview

Triple-negative breast cancer (TNBC) is an aggressive subtype of breast cancer lacking hormone receptors and HER2, making it particularly hard to treat. Aptamers have emerged as promising molecules in targeted therapy.

This project focuses on structurally validating the interaction between the Apt2 aptamer—previously developed via cell-SELEX—and its putative targets in the TNBC cell line MDA-MB-231 using computational methodologies.

### 🎯 Objectives

- Predict and refine the 2D and 3D structures of Apt2 (with and without flanking primers).
- Model the structure of six protein targets identified by prior proteomics.
- Simulate molecular docking between Apt2 and the protein targets.
- Analyze the molecular interactions using structure-based contact prediction tools.

### 🧪 Methodology

1. **Secondary Structure Prediction**  
   - Tool: [Mfold](http://unafold.rna.albany.edu/?q=mfold)
   - Output: Dot-bracket format for 3D modeling

2. **Tertiary Structure Modeling**  
   - Tool: [3dDNA](http://biophy.hust.edu.cn/new/)
   - Followed by Molecular Dynamics using AMBER20

3. **Protein Modeling**  
   - Tool: [AlphaFold](https://www.deepmind.com/open-source/alphafold)
   - Based on UniProt sequences and known oligomeric states

4. **Molecular Docking**  
   - Tool: [HADDOCK 2.4](https://wenmr.science.uu.nl/haddock2.4/)
   - Docking was guided by ambiguous interaction restraints (AIRs)

5. **Interaction Analysis**  
   - Tool: [RING 3.0](http://protein.bio.unipd.it/ring/)
   - For classifying H-bonds, VDW, π–π stacking and other contacts

6. **Visualization & Structural Validation**  
   - Tools: PyMOL, VARNA


### 📌 Notes

- All sequences and models are publicly available or derived from UniProt.
- The aptamer used was 49 nucleotides long, excluding flanking primer regions.
- This project was part of the Master in Bioinformatics, University of Minho.
