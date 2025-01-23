# Installation

## Prerequisites

- **Python**: Ensure you have Python 3.7 or higher installed.
- **Hail**: Required for VariantDataset operations.
- **PySpark**: Necessary for distributed data processing.

## Install via PyPI

You can install the package using `pip`:

```bash
pip install gvcf_to_vds_pipeline
```

## Clone from GitHub

Alternatively, clone the repository and install locally:

```bash
git clone https://github.com/OligoGeneticDiseases/gvcf-to-vds-pipeline.git
cd gvcf-to-vds-pipeline
pip install .
```
## Verify Installation

After installation, verify that the CLI tool is accessible:

```bash
gvcf-to-vds --help
```