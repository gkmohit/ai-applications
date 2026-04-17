# Hierarchical Section Numbering Summary
## CanadianTransactionClassifier Jupyter Notebook

**Document Created**: April 15, 2026  
**Notebook**: CanadianTransactionClassifier-CTC.ipynb  
**Total Cells**: 105  
**Section Levels**: 3 (Major Sections, Subsections, Individual Cells)

---

## Numbering Scheme Overview

The notebook now follows a **3-level hierarchical numbering system**:

| Level | Format | Example | Description |
|-------|--------|---------|-------------|
| **Level 1** | `Section N` | Section 1, Section 2 | Major workflow phases (8 total) |
| **Level 2** | `N.N` | 1.1, 2.3, 5.2 | Logical subsections within phases |
| **Level 3** | `N.N.N` | 1.1.1, 5.2.3 | Individual cells/tasks (37 total) |

---

## Section Structure

### **Section 1: Environment Setup** (Cells 1-13)
Main objective: Configure computing environment, install dependencies, and prepare for model training.

| Subsection | Content | Cells |
|------------|---------|-------|
| **1.1 Setup and Dependencies** | Install required Python packages | 2 |
| **1.2 Compute Device Configuration** | Detect GPU/TPU/CPU, verify device setup | 3-7 |
| **1.3 Google Drive Integration** | Mount Google Drive for persistent storage | 8-12 |
| **1.4 Import Libraries** | Import all required ML/DL libraries | 10-13 |

*Level 3 Tasks*:
- 1.1.1: Install required packages (pip installation)
- 1.2.1: Configure device usage setup
- 1.2.2: Device configuration verification
- 1.2.3: Verify device for model training
- 1.4.1: Import all required libraries

---

### **Section 2: Data Loading and Preprocessing** (Cells 14-26)
Main objective: Download transaction dataset, authenticate with HuggingFace, explore structure, and understand data characteristics.

| Subsection | Content | Cells |
|------------|---------|-------|
| **2.1 Download Dataset** | HuggingFace authentication and dataset loading | 14-19 |
| **2.2 Data Preprocessing** | Explore dataset structure, identify columns | 20-22 |
| **2.3 CRA T2125 Mapping** | Map transaction categories to Canadian tax codes | 23-24 |

*Level 3 Tasks*:
- 2.1.1: Hugging Face authentication setup
- 2.1.2: Download transaction dataset
- 2.2.1: Explore dataset structure
- 2.3.1: CRA T2125 category mapping

---

### **Section 3: Feature Engineering** (Cells 25-27)
Main objective: Prepare text data for machine learning by encoding labels and structuring features.

| Subsection | Content | Cells |
|------------|---------|-------|
| **3.1 Data Preparation** | Encode labels, create train/test arrays | 25-27 |

*Level 3 Tasks*:
- 3.1.1: Prepare data for training (text and label extraction)

---

### **Section 4: Model Training (Original)** (Cells 28-67)
Main objective: Train 5 different ML algorithms and compare performance on test data.

| Subsection | Content | Cells |
|------------|---------|-------|
| **4.1 Logistic Regression** | TF-IDF features + Logistic Regression training | 28-32 |
| **4.2 Linear SVM** | Support Vector Machine with TF-IDF features | 33-35 |
| **4.3 LightGBM** | Gradient boosting framework training | 36-38 |
| **4.4 DistilBERT** | Transformer model (deep learning) training | 39-41 |
| **4.5 MobileBERT** | Mobile-optimized variant (placeholder) | 42-43 |
| **4.6 Model Comparison** | Compare all 5 models, identify best | 66-67 |

*Level 3 Tasks*:
- 4.1.1: Train Logistic Regression model
- 4.2.1: Train Linear SVM
- 4.3.1: Train LightGBM
- 4.4.1: Train DistilBERT
- 4.5.1: MobileBERT variant
- 4.6.1: Model comparison and results

---

### **Section 5: Epoch Experiments** (Cells 44-65)
Main objective: Determine optimal training duration by testing each model across multiple epoch counts (25, 50, 75, 100).

| Subsection | Content | Cells |
|------------|---------|-------|
| **5.1 Memory & GPU Setup** | Memory optimization, GPU configuration, monitoring | 44-50 |
| **5.2 Epoch Experimentation** | Train models with different epoch counts, analyze convergence | 51-65 |

*Level 3 Tasks*:
- 5.1.1: Memory optimization and check
- 5.1.2: GPU memory monitoring setup
- 5.1.3: GPU helper functions creation
- 5.1.4: Pre-epoch GPU setup
- 5.1.5: GPU vs TPU comparison
- 5.1.6: Data usage summary
- 5.2.1: Epoch experiment helper functions
- 5.2.2-14: Epoch training for each model
- 5.2.15: Epoch experiment setup

---

### **Section 6: Results Export and Archive** (Cells 68-75)
Main objective: Export all training results, create visualizations, generate reports, and document findings.

| Subsection | Content | Cells |
|------------|---------|-------|
| **6.1 Visualization** | Create comparison charts (accuracy, F1, precision/recall) | 68-69 |
| **6.2 Classification Reports** | Generate per-class performance metrics | 70-71 |
| **6.3 Export Results** | Save epoch results, model comparison to CSV/JSON | 72-74 |

*Level 3 Tasks*:
- 6.1.1: Create visualization charts
- 6.2.1: Generate classification reports
- 6.3.1: Export results to files

---

### **Section 7: ONNX Model Export** (Cells 76-77)
Main objective: Export best-performing model to ONNX format for cross-platform deployment.

| Subsection | Content | Cells |
|------------|---------|-------|
| **7.1 ONNX Export** | Convert best model to ONNX format, save vectorizer | 76-77 |

*Level 3 Tasks*:
- 7.1.1: Export best model to ONNX format

---

### **Section 8: Final Summary** (Cells 78-82)
Main objective: Archive all models, generate summary reports, and provide deployment recommendations.

| Subsection | Content | Cells |
|------------|---------|-------|
| **8.1 Save Models** | Pickle serialize all trained models | 78-79 |
| **8.2 Executive Summary** | Generate comprehensive JSON summary | 80-81 |
| **8.3 Final Results** | Display final metrics and next steps | 82 |

*Level 3 Tasks*:
- 8.1.1: Save all trained models to pickle files
- 8.2.1: Generate executive summary report
- 8.3.1: Display final project results

---

## Numbering Format Guide

### Markdown Headers
```markdown
## Section 1: Environment Setup
### 1.1 Setup and Dependencies
### 1.2 Compute Device Configuration
## Section 2: Data Loading and Preprocessing
### 2.1 Download Dataset
### 2.1.1 Hugging Face Authentication
```

### Code Cell Comments
```python
# Section 1.1.1: Install Dependencies
import sys
import subprocess
...

# Section 2.1.2: Download Dataset
from datasets import load_dataset
...

# Section 5.2.3: Accuracy vs Training Time Visualization
fig, axes = plt.subplots(1, 2, figsize=(14, 5))
...
```

---

## Key Statistics

| Metric | Count |
|--------|-------|
| **Total Cells** | 105 |
| **Markdown Cells** | 34 |
| **Code Cells** | 71 |
| **Major Sections (Level 1)** | 8 |
| **Subsections (Level 2)** | ~25 |
| **Code cells with Level 3 markers** | 37 |
| **Lines of Code** | ~4,500+ |
| **Execution Time** | 1-3 hours (GPU) / 6-8 hours (CPU) |

---

## Navigation Guide

### By Workflow Phase
- **Setup Phase**: Sections 1-3 (Cells 1-27)
- **Model Training Phase**: Sections 4-5 (Cells 28-65)
- **Results Phase**: Sections 6-8 (Cells 66-105)

### By Purpose
- **Configuration**: Section 1 (Cells 1-13)
- **Data**: Section 2 (Cells 14-26)
- **ML Models**: Sections 4-5 (Cells 28-65)
- **Analysis/Export**: Sections 6-8 (Cells 66-105)

### Quick Jump Points
- Install packages: Section 1.1.1 (Cell 2)
- Download data: Section 2.1.2 (Cell 17)
- Train Logistic Regression: Section 4.1 (Cells 28-32)
- Configure GPU for epochs: Section 5.1 (Cells 44-50)
- Export ONNX: Section 7.1 (Cells 76-77)
- Final results: Section 8.3 (Cell 82)

---

## Benefits of This Structure

1. **Clarity**: Section numbers make it easy to reference specific parts
2. **Organization**: Hierarchical structure reflects logical workflow
3. **Scalability**: Easy to add new subsections with consistent numbering
4. **Documentation**: Clear mapping between notebook cells and tasks
5. **Reproducibility**: Section numbers aid in documenting procedures
6. **Teaching**: Students can easily understand notebook structure
7. **Maintenance**: Future updates can maintain consistent numbering
8. **Collaboration**: Team members can reference sections by number

---

## Example References

Instead of saying "the cell that trains Logistic Regression models", you can now say:
- "Section 4.1.1 covers Logistic Regression training"
- "See Section 5.2.1 for epoch experiment setup"
- "Results export is documented in Section 6.3"

---

## Future Updates

When adding new cells or sections, maintain this numbering scheme:
- New subsections: Increment Level 2 (e.g., 5.3, 5.4)
- New tasks within subsections: Increment Level 3 (e.g., 5.2.16, 5.2.17)
- New major sections: Only if workflow changes significantly
- Update this document whenever sections are added/modified

---

**Note**: This section numbering scheme was systematically applied to enhance notebook organization and navigability. All markdown headers and major code cells now include section numbers for easy reference and documentation.
