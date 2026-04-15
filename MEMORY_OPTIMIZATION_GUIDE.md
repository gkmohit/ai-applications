# Google Colab Memory Optimization Guide

## Problem: "Your session crashed after using all available RAM"

This error occurs in Google Colab when:
- Training large transformer models (DistilBERT)
- Processing large datasets
- Running multiple epoch experiments
- Batch sizes are too large
- Models are kept in memory unnecessarily

## Solutions (In Priority Order)

### Solution 1: Use GPU Runtime (Fastest Fix)
In Google Colab:
1. Click **Runtime** menu
2. Select **Change runtime type**
3. Choose **GPU** (or **TPU** if available)
4. Click **Save**
5. Re-run your notebook

**Why it works:** GPU has dedicated VRAM (12-16GB) separate from system RAM
**Training speedup:** 5-10x faster

### Solution 2: Reduce Batch Size
In the notebook, modify the memory configuration:

```python
memory_config['distilbert_batch_size'] = 4  # Reduce from 8 to 4
```

How batch size affects memory:
- Batch size 16 → ~8GB RAM
- Batch size 8 → ~4GB RAM
- Batch size 4 → ~2GB RAM
- Batch size 1 → Minimum (very slow)

### Solution 3: Skip Resource-Heavy Models
Modify the epoch experiments setup cell:

```python
memory_config['skip_distilbert_epochs'] = True   # Skip transformer training
memory_config['skip_mobilebert_epochs'] = True   # Skip mobile model
```

This allows you to train only classical models (LR, SVM, LGB) which use ~1-2GB.

### Solution 4: Run Models Selectively
Instead of all epoch experiments, run only CPU-friendly models first:

```python
# Only run these cells in this order:
# Cell 46: Logistic Regression epochs      (~30 seconds, <500MB)
# Cell 47: Linear SVM epochs               (~1 minute, <500MB)
# Cell 48: LightGBM epochs                 (~1 minute, <1GB)
# Skip Cell 50: DistilBERT epochs          (skip until GPU is available)
# Skip Cell 53: MobileBERT epochs          (skip until GPU is available)
```

### Solution 5: Clear Memory Between Sections
Run this cell to free up memory:

```python
import gc
import torch

gc.collect()  # Python garbage collection
if torch.cuda.is_available():
    torch.cuda.empty_cache()  # GPU cache
```

### Solution 6: Restart Colab Session
If you've already crashed:
1. Click **Runtime** menu
2. Select **Restart runtime**
3. Start from the top of the notebook

## Memory Requirements by Model

| Model | Memory | Time (CPU) | Time (GPU) |
|-------|--------|-----------|-----------|
| Logistic Regression | ~200MB | 30s | 10s |
| Linear SVM | ~300MB | 1m | 30s |
| LightGBM | ~1GB | 1m | 20s |
| DistilBERT (1 epoch) | ~3-4GB | 5-10m | 30s |
| DistilBERT (4 epochs) | ~3-4GB | 20-40m | 2m |
| All 5 models × 4 epochs | ~5-8GB | 70-100m | 5-10m |

## Recommended Workflow for Limited Memory

**Step 1: Check Available Memory**
```python
import psutil
memory = psutil.virtual_memory()
print(f"Available: {memory.available / (1024**3):.1f} GB")
```

**Step 2: Run by Memory Tier**
- **If < 2GB available:** CPU-only models (LR, SVM, LGB)
- **If 2-5GB available:** Use GPU runtime or skip DistilBERT
- **If 5-8GB available:** Run all models on CPU or with reduced epochs
- **If 8GB+ available:** Run everything

**Step 3: Export Results**
```python
# Save results before clearing
comparison_df.to_csv('results.csv')
epoch_experiment_results_df.to_json('epoch_results.json')
```

## Technical Details

### Why Transformers Use So Much Memory
- **DistilBERT model:** ~270MB
- **Tokenized dataset:** ~500MB - 2GB (depends on dataset size)
- **DataLoaders and batches:** ~2-3GB
- **Optimizer state:** ~500MB - 1GB
- **Gradients:** ~1-2GB during backprop

### Memory Optimization Techniques Added
✅ Gradient checkpointing (enabled in notebook)
✅ Batch size reduction based on available RAM
✅ Model reuse (don't load repeatedly)
✅ Garbage collection after each model
✅ GPU cache clearing

## Quick Fixes Checklist

- [ ] Try GPU runtime first (90% of issues resolved)
- [ ] Reduce batch size to 4
- [ ] Skip DistilBERT/MobileBERT  epochs
- [ ] Run classical models separately
- [ ] Clear memory between sections
- [ ] Restart Colab session
- [ ] Use free tier with CPU if needed
- [ ] Consider Colab Pro for more resources

## Getting More Resources

### Free Option
- Use GPU runtime (random allocation, may take 1-2 restarts)
- Limit to classical models only
- Run during off-peak hours (better availability)

### Paid Option (Colab Pro)
- $10/month for guaranteed GPU/TPU access
- 24-hour GPU sessions
- Run full experiments without interruption

## If Problems Persist

1. **Clear browser cache:** Colab → Settings → Clear cache
2. **Use incognito mode:** Fresh session without extensions
3. **Contact Colab support:** With error message and cell number
4. **Run locally:** Install PyTorch + transformers locally (if you have GPU)

## Monitoring Memory in Real-Time

Add this to monitor during execution:

```python
# For GPU
!nvidia-smi --query-gpu=memory.used,memory.total --format=csv,noheader

# For CPU
!free -h

# Python monitoring
import psutil
process = psutil.Process()
print(f"RAM used: {process.memory_info().rss / (1024**3):.2f} GB")
```

## Summary

| Issue | Fix | Time |
|-------|-----|------|
| RAM crashed | Use GPU | Immediate |
| OOM during training | Reduce batch to 4 | Immediate |
| Still slow | Skip transformers | Immediate |
| Need all models | Use Colab Pro | Permanent |

Start with **GPU runtime** - it solves 90% of memory issues!
