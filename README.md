# CH374-Sulfur_Absorbtivity_to_Copper_Stills
Computational approach to view how sulfur byproducts that are produced during fermentation stick to the walls of copper stills. This was done on three FCC (Cu100, Cu110, Cu111)
# Sulfur Absorptivity to Copper Stills
**Rowdy Smith**  
*Physical Chemistry II (CH374)*  
**Date:** April 27, 2026  

---

## Table of Contents
- [Project Overview](#project-overview)
- [Methods](#methods)
- [Results](#results)
- [File Structure](#file-structure)
- [Navigation Instructions](#navigation-instructions)
- [Prerequisites](#prerequisites)

---

## Project Overview
This project presents a density functional theory (DFT) investigation into the interaction between sulfur-containing fermentation byproducts and copper surfaces. The goal is to evaluate whether adsorption to copper still walls can be accurately modeled computationally.

Sulfur compounds studied:
- Hydrogen sulfide (H₂S)  
- Methanethiol (CH₃SH)  
- Dimethyl sulfide ((CH₃)₂S)  
- Dimethyl disulfide (CH₃SSCH₃)  

These compounds contribute to undesirable off-flavors in fermented beverages. Understanding their interaction with copper is important in brewing and distillation.

---

## Methods
- **Software:** Quantum ESPRESSO  
- **Theory Level:** DFT with PBE exchange–correlation functional  

### Surface Models
- Cu(100)  
- Cu(110)  
- Cu(111)  

### Workflow
1. Molecules constructed and pre-optimized in WebMO  
2. Re-optimized in Quantum ESPRESSO  
3. Copper slabs generated from bulk copper  
4. Structural optimizations performed with:
   - Plane-wave cutoff energy: 50 Ry  

### Adsorption Energy Equation
```
E_ads = E(slab + molecule) - E(slab) - E(molecule)
```

---

## Results
### Cu(100) and Cu(110)
- Similar adsorption behavior across molecules  
- Cu(110) slightly less favorable (more positive energies)

### Cu(111)
- Much weaker adsorption overall  
- DMS and DMDS show minimal binding  
- H₂S and CH₃SH still bind, but less strongly  

### Key Insight
- Copper removes smaller, reactive sulfur compounds effectively  
- Larger molecules (DMS, DMDS) are harder to remove  
- Surface structure strongly affects adsorption  

---

## File Structure
```
Cu/
├── Cu100_*.out
├── Cu100_*.xyz
├── Cu110_*.out
├── Cu110_*.xyz
├── Cu111_*.out
├── Cu111_*.xyz
```

### Description
- `Cu/` → Main project folder  
- File prefixes indicate surface type:
  - Cu100 → Cu(100)
  - Cu110 → Cu(110)
  - Cu111 → Cu(111)

### File Types
- `.out` → Quantum ESPRESSO output files (energies + final structures)  
- `.xyz` → Geometry files for visualization  

---

## Navigation Instructions
1. Open the `Cu/` folder  
2. Choose files based on surface type (Cu100, Cu110, Cu111)  
3. Use:
   - `.out` files → Extract energies  
   - `.xyz` files → Visualize structures  

---

## Prerequisites
- Quantum ESPRESSO  
- WebMO (or similar molecular builder)  
- Visualization software (ASE, VMD, or Avogadro)  

### Recommended Knowledge
- Density Functional Theory (DFT) basics  
- Surface/slab modeling  
- Adsorption energy calculations  

---

## Summary
This project shows that computational chemistry can predict how sulfur compounds interact with copper surfaces. It explains why copper stills help remove off-flavors and why some compounds persist.
