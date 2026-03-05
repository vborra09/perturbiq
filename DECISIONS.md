# PerturbIQ Architecture Decision Log

## ADR-001: Project Language and Runtime
Date: [DATE]
Decision: Python 3.12, Miniconda environment management
Reasoning: Standard for bioinformatics ecosystem. Conda handles
           complex dependency resolution better than pip alone
           for packages like PyTorch Geometric and Scanpy.
Alternatives considered: Docker-only development
Revisit if: Major dependency conflict arises

