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

### Example: Convert GVCFs to VDS

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


### `readgvcfs`

Creates or updates a VDS by combining new GVCFs and/or an existing VDS.

**Basic Command**:

```bash
gvcf-to-vds readgvcfs \
  -f /path/to/gvcfs_or_dir \
  -d /path/to/dest.vds \
  --temp /tmp/combine-temp \
  --use_genome_intervals \
  --save_plan /path/to/combine-plan.json
```

Key Options:
*	-f, --file: GVCF file(s) or directory(ies).
*	--vds_in: (Optional) Path to an existing VDS to combine into.
*	-d, --dest: Output VDS path.
*	--temp: Temporary directory for intermediate files.
*	--use_genome_intervals or --use_exome_intervals: Hail default partitioning.
*	--intervals: Custom intervals (e.g., chr1:1-1000000).
*	--import_interval_size: Size of intervals for GVCF partitioning.

### ```filter_samples```

Includes or excludes specific samples from a VDS.

```bash
gvcf-to-vds filter_samples \
  -v /path/to/vds \
  -s sample_file.txt \
  -k \
  -o /path/to/output.vds
```

* -v, --vds: Input VDS path.
* -s, --samples: Text file with one sample ID per line.
* -k, --keep: If provided, keeps listed samples; otherwise removes them.
* -o, --out: Output path (overwrites if omitted).

filter_intervals

Filters intervals in a VDS (either keeping or removing them).

```bash
gvcf-to-vds filter_intervals \
  -v /path/to/input.vds \
  -i chr1:1-1000000 chr2:500-1500 \
  --keep \
  -o /path/to/output.vds
```
* -v, --vds: Input VDS path.
* -i, --intervals: One or more intervals (Hail locus format).
* --keep: Keep these intervals (default). If not set, remove them.
* -o, --out: Output VDS path.

### ```sample_qc```

Computes sample quality metrics on a VDS. Exports results to a file or prints to stdout.
 
```bash
gvcf-to-vds sample_qc \
  -v /path/to/input.vds \
  -o /path/to/output.tsv
```

* -v, --vds: Input VDS path.
* -o, --out: Output table file (default prints to console).

### ```split_multi```

Splits multi-allelic variants.
 
```bash
gvcf-to-vds split_multi \
  -v /path/to/input.vds \
  -o /path/to/split.vds \
  --filter_changed_loci
```

* -v, --vds: Input VDS.
* -o, --out: Output (split) VDS.
* --filter_changed_loci: If set, filters variants whose locus changes after splitting.

### ```to_dense_mt```

Converts the sparse VDS representation into a dense Hail MatrixTable.

```bash
gvcf-to-vds to_dense_mt \
  -v /path/to/input.vds \
  -o /path/to/dense.mt
```

* -v, --vds: Input VDS.
* -o, --out: Output dense MatrixTable path.