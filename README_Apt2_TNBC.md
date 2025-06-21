# Apt2-TNBC Binding Characterization

This repository contains the bioinformatics pipeline and supporting files for the project:

**"Identification of new breast cancer-related biomarkers via integrated bioinformatics analysis and experimental validation"**  
by *Inês Lameira, University of Minho*

## 🧬 Overview

Triple-negative breast cancer (TNBC) is an aggressive subtype of breast cancer lacking hormone receptors and HER2, making it particularly hard to treat. Aptamers have emerged as promising molecules in targeted therapy.

This project focuses on structurally validating the interaction between the Apt2 aptamer—previously developed via cell-SELEX—and its putative targets in the TNBC cell line MDA-MB-231 using computational methodologies.

## 🎯 Objectives

- Predict and refine the 2D and 3D structures of Apt2 (with and without flanking primers).
- Model the structure of six protein targets identified by prior proteomics.
- Simulate molecular docking between Apt2 and the protein targets.
- Analyze the molecular interactions using structure-based contact prediction tools.
- Highlight strengths and limitations of in silico predictions to support experimental planning.

## 🧪 Methodology

1. **Secondary Structure Prediction**  
   - Tool: [Mfold](http://unafold.rna.albany.edu/?q=mfold)
   - Output: Dot-bracket format for 3D modeling

2. **Tertiary Structure Modeling**  
   - Tool: [3dDNA](http://biophy.hust.edu.cn/3dDNA/)
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
   - Tools: PyMOL, UCSF Chimera

## 🧾 File Structure

```
/aptamer_structure/        # Apt2 2D and 3D models (before and after MD)
/protein_models/           # AlphaFold structures for all six targets
/docking_results/          # HADDOCK docking complexes and scores
/interactions/             # RING contact tables for each complex
/report/                   # Final LaTeX + PDF write-up and presentation
```

## 📚 References

Relevant literature cited throughout the report, including:
- [Ferreira et al. 2021](https://doi.org/10.1038/s41598-021-87998-y)
- [Bergonzo & Grishaev 2025](https://doi.org/10.1021/acs.jcim.5c00245)
- [Alkhamis et al. 2025](https://doi.org/10.1093/nar/gkaf219)
- Full reference list available in `report/references.bib`.

## 🚀 Getting Started

To replicate the analysis:

1. Clone the repo  
   `git clone https://github.com/yourusername/Apt2-TNBC.git`

2. Install AMBER20 or use a Docker container with it preinstalled.

3. Run MD scripts in `/aptamer_structure/` followed by docking via HADDOCK server.

4. Use `ring.py` or access the RING 3.0 web server for interaction analysis.

## 📌 Notes

- All sequences and models are publicly available or derived from UniProt.
- The aptamer used was 49 nucleotides long, excluding flanking primer regions.
- This project was part of the Master in Bioinformatics, University of Minho.