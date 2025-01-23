# Usage

The **GVCF to VDS Pipeline** provides a command-line interface (CLI) to perform various operations. Below are the primary commands and their usage.

## Available Commands

- `readgvcfs`: Combine GVCF files into a VDS.
- `filter_samples`: Filter samples in a VariantDataset.
- `filter_intervals`: Filter intervals in a VDS.
- `sample_qc`: Compute sample quality control metrics.
- `split_multi`: Split multi-allelic variants in a VDS.
- `to_dense_mt`: Convert a VariantDataset to a dense MatrixTable.

## Command Syntax

```bash
gvcf-to-vds <command> [options]
```
## Example: Convert GVCFs to VDS

The `readgvcfs` command reads GVCF files and converts them to VDS format.

```bash
gvcf-to-vds readgvcfs \
  -f /path/to/gvcf_files \
  -d /path/to/output_vds \
  --temp /path/to/temp_dir \
  --use_genome_intervals
```

## Detailed Command Usage

For detailed information on each command, use the --help flag:

```bash
gvcf-to-vds <command> --help
```

Example

```bash
gvcf-to-vds readgvcfs --help
```