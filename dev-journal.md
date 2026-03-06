## Session 1 — [6th march]

### What We Built
- GitHub repository created and pushed live (github.com/vborra09/perturbiq)
- Full project directory structure created (20+ folders)
- Conda environment (perturbiq, Python 3.10) with all dependencies
- VSCode configured with correct interpreter and extensions
- PyTorch fundamentals completed (toy gene expression network)
- Google Colab configured, repo cloned, core dependencies installed

### Decisions Made and WHY
- Python 3.10 over 3.12: PyTorch Geometric most stable on 3.10
- CPU install locally, GPU only on Colab: preserves compute units
- T4 GPU for training, never premium GPU: 400 units must last whole project
- Skipped pyg_lib and C++ extensions in Colab: PyTorch 2.10+cu128 too new,
  no pre-compiled wheels exist yet. Will revisit when GNN phase begins.
- Skipped committing toy network: learning exercise, not project code

### What I Now Understand
- What a tensor is and why PyTorch uses them over numpy arrays
- What a forward pass is (data flows through layers, computation graph built)
- What loss function measures (how wrong predictions are, MSELoss formula)
- What backpropagation does (walks computation graph backwards, computes gradients)
- What an optimizer does (uses gradients to update weights, Adam explained)
- What a training loop looks like: zero_grad → forward → loss → backward → step
- Why we always validate separately with torch.no_grad()
- Pearson R as evaluation metric — our toy network achieved R=0.9866
- Why individual neuron weights are not directly interpretable (distributed representations)
- Colab compute unit strategy — CPU for setup, T4 only for training runs

### Errors Hit and How We Fixed Them
- pkg_resources missing: fixed with pip install setuptools==70.0.0
- scikit-learn conflict with umap-learn: upgraded to scikit-learn==1.6.1
- pyg_lib not available for PyTorch 2.10+cu128: skipped, install deferred to GNN phase
- torch_scatter building from source (>15 min): stopped, deferred to GNN phase
- Syntax error in f-string in Colab GPU check: fixed immediately

### What I Don't Fully Understand Yet
- Exactly how Adam's adaptive learning rate works mathematically
- What happens inside torch.no_grad() at the computation graph level
- Why distributed representations make individual neuron interpretation hard

### Next Session Starts At
- Day 1 of project code: Data Pipeline
- First file: pipelines/data/download.py
- First task: locate and download Norman 2019 dataset
- Before writing any code: inspect what the raw data looks like
