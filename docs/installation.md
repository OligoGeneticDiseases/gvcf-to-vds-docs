# Installation

## Prerequisites

- **Python**: Ensure you have Python 3.7 or higher installed.
- **Hail**: Required for VariantDataset operations.
- **PySpark**: Necessary for distributed data processing.

## Install via PyPI

You can install the package using `pip`:

## Steps

1. **Clone the repository**:
```bash
git clone https://github.com/OligoGeneticDiseases/gvcf-to-vds-pipeline.git
cd gvcf-to-vds-pipeline
```

2.	(Optional) Create a virtual environment:
```bash
python3 -m venv venv
source venv/bin/activate
```

3.	Install:
```bash
pip install .
```

* This will install all necessary Python dependencies and a console script gvcf-to-vds.

Verifying Installation
* After install, run gvcf-to-vds --help. You should see a help message for the CLI.
* Ensure that import hail works in a Python REPL. You may need to install or configure Spark/Hail if not already done.

Troubleshooting
* If you encounter Spark/Hail import errors, verify your environment variables and Java installations.
* Mac OS or Windows users may need additional setup for PySpark. See Hail’s platform notes.


## Verify Installation

After installation, verify that the CLI tool is accessible:

```bash
gvcf-to-vds --help
```
