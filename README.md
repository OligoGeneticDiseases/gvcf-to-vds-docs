# GVCF to VDS Pipeline Documentation

THis is the **GVCF to VDS Pipeline** documentation repository. This site provides comprehensive guides, usage instructions, API references, and contribution guidelines for the GVCF to VDS Pipeline tool.

## Table of Contents

- [Installation](installation.md)
- [Usage](usage.md)
- [API Reference](api_reference.md)
- [Contributing](contributing.md)

## Building the Documentation Locally

To build the documentation on your local machine, follow these steps:

1. **Clone the Repository**

```bash
git clone https://github.com/oligogeneticdiseases/gvcf-to-vds-docs.git
cd gvcf-to-vds-docs
```

## How to edit and build

```bash
pip install mkdocs
```
* use `mkdocs serve` to dynamically build the pages on localhost while editing the markdown files

* run `mkdocs gh-deploy`: builds the html and pushes to branch `gh-pages` (which is the one being served)

* commit and push the changes to the markdown files to branch `main`