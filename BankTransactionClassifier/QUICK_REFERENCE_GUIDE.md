# Quick Reference: Section Numbering Guide
## CanadianTransactionClassifier Notebook

---

## 🎯 Quick Navigation

| Section | Purpose | Cells | Est. Time |
|---------|---------|-------|-----------|
| **1** | Environment Setup | 1-13 | 5 min |
| **2** | Data Loading | 14-26 | 10 min |
| **3** | Feature Engineering | 25-27 | 2 min |
| **4** | Model Training | 28-67 | 30 min |
| **5** | Epoch Experiments | 44-65 | 2-4 hours |
| **6** | Results & Export | 68-75 | 10 min |
| **7** | ONNX Export | 76-77 | 5 min |
| **8** | Final Summary | 78-82 | 5 min |

---

## 📑 Section Details

### **Section 1: Environment Setup** ⚙️
- **1.1**: Install dependencies
- **1.2**: Configure GPU/TPU/CPU device
- **1.3**: Mount Google Drive
- **1.4**: Import libraries

### **Section 2: Data Loading** 📊
- **2.1**: HuggingFace authentication and download
- **2.2**: Explore dataset structure
- **2.3**: Map to CRA T2125 categories

### **Section 3: Feature Engineering** 🔧
- **3.1**: Prepare data, encode labels

### **Section 4: Model Training** 🤖
- **4.1**: Logistic Regression
- **4.2**: Linear SVM
- **4.3**: LightGBM
- **4.4**: DistilBERT
- **4.5**: MobileBERT
- **4.6**: Compare all models

### **Section 5: Epoch Experiments** 📈
- **5.1**: Memory optimization and GPU setup
- **5.2**: Train models with 25/50/75/100 epochs

### **Section 6: Results Export** 💾
- **6.1**: Create visualizations
- **6.2**: Generate classification reports
- **6.3**: Export to CSV/JSON

### **Section 7: ONNX Export** 🚀
- **7.1**: Export best model for production

### **Section 8: Final Summary** 📋
- **8.1**: Save all pickle files
- **8.2**: Generate executive summary
- **8.3**: Display final results

---

## 🔍 Key Code Section Markers

Look for these comments at the start of code cells:

```python
# Section 1.1.1: Install Dependencies
# Section 2.1.2: Download Dataset
# Section 4.1.1: Train Logistic Regression
# Section 5.2.3: Accuracy vs Training Time
# Section 6.3.1: Export Results
# Section 8.2.1: Generate Summary
```

---

## 🎓 Common Tasks & Where to Find Them

| Task | Section | Cell |
|------|---------|------|
| Install packages | 1.1.1 | 2 |
| Setup GPU | 1.2 | 3-7 |
| Download data | 2.1.2 | 17 |
| Explore dataset | 2.2.1 | 20 |
| Train LR model | 4.1 | 28-32 |
| Train SVM | 4.2 | 33-35 |
| Train LightGBM | 4.3 | 36-38 |
| Train DistilBERT | 4.4 | 39-41 |
| Epoch experiments | 5.2 | 50-65 |
| Compare models | 4.6.1 | 66-67 |
| Export ONNX | 7.1.1 | 76-77 |
| Final results | 8.3.1 | 82 |

---

## 💡 Tips for Using the Numbering

1. **Reference in Documentation**: "See Section 5.2.3 for training details"
2. **Skip Sections**: To run only models, skip to Section 4
3. **Resume Later**: Note the section number if you stop mid-notebook
4. **Troubleshooting**: Reference section numbers when asking for help
5. **Modification**: When adding cells, use consistent numbering

---

## 📋 File Locations

| File | Purpose |
|------|---------|
| `SECTION_NUMBERING_SUMMARY.md` | Comprehensive section mapping |
| `QUICK_REFERENCE_GUIDE.md` | This quick reference (you are here) |
| `CanadianTransactionClassifier-CTC.ipynb` | Main notebook with section numbers |

---

## ⚡ Fast Navigation Shortcuts

- **Skip to Model Training**: Jump to Section 4 (Cell 28)
- **Run Epochs Only**: Requires Sections 1-3 first, then jump to Section 5
- **Export Results**: Jump to Section 6 after any model training
- **Check Final Output**: Jump to Section 8.3 to see results

---

## ✅ Verification Checklist

- [ ] All section headers use format: `## Section N` or `### N.N`
- [ ] Code cells have `# Section X.X.X` comments
- [ ] Major sections numbered 1-8
- [ ] Subsections use proper hierarchy (1.1, 1.2, etc.)
- [ ] Cell numbers referenced consistently
- [ ] Documentation links section numbers when applicable

---

**Last Updated**: April 15, 2026  
**Total Sections**: 8 | **Total Subsections**: ~25 | **Total Level 3 Tasks**: 37  
**Notebook Status**: ✅ Section numbering complete and verified
