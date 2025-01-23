# API Reference

## `gvcf_to_vds_pipeline.cli.command_setup`

### `setup_parser()`

Sets up the argument parser for the CLI tool.

**Returns:**

- `argparse.ArgumentParser`: Configured argument parser.

### `command_handlers(args, conf)`

Retrieves the appropriate handler function based on the command.

**Parameters:**

- `args`: Parsed command-line arguments.
- `conf`: Configuration for Spark/Hail.

**Returns:**

- `dict`: Mapping of commands to their handler functions.

### `setup_spark_config(args)`

Configures Spark settings based on provided arguments.

**Parameters:**

- `args`: Parsed command-line arguments.

**Returns:**

- `SparkConf`: Configured Spark configuration.

## `gvcf_to_vds_pipeline.data_processing.gvcf.process`

### `build_or_combine_vds(gvcf_paths, output_path, existing_vds=None)`

Combines multiple GVCF files into a single VDS.

**Parameters:**

- `gvcf_paths (list)`: List of paths to GVCF files.
- `output_path (str)`: Path to save the combined VDS.
- `existing_vds (str, optional)`: Path to an existing VDS to update.

**Returns:**

- `None`

## `gvcf_to_vds_pipeline.data_processing.gvcf.read`

### `read_gvcf(file_path)`

Reads a single GVCF file.

**Parameters:**

- `file_path (str)`: Path to the GVCF file.

**Returns:**

- `VariantDataset`: Parsed VariantDataset.

## `gvcf_to_vds_pipeline.data_processing.vds.operations`

### `filter_samples(vds, samples_to_keep)`

Filters samples in the VDS.

**Parameters:**

- `vds (VariantDataset)`: The original VariantDataset.
- `samples_to_keep (list)`: List of sample IDs to retain.

**Returns:**

- `VariantDataset`: Filtered VariantDataset.

### `split_multi(vds)`

Splits multi-allelic variants in the VDS.

**Parameters:**

- `vds (VariantDataset)`: The original VariantDataset.

**Returns:**

- `VariantDataset`: VariantDataset with split multi-allelic variants.

## `gvcf_to_vds_pipeline.utils.config`

### `load_config(config_path)`

Loads configuration from a JSON file.

**Parameters:**

- `config_path (str)`: Path to the JSON configuration file.

**Returns:**

- `dict`: Configuration data.

## `gvcf_to_vds_pipeline.utils.logging`

### `setup_logging(log_level)`

Configures logging for the application.

**Parameters:**

- `log_level (str)`: Logging level (e.g., 'INFO', 'DEBUG').

**Returns:**

- `logging.Logger`: Configured logger.