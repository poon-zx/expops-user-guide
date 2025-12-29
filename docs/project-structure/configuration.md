# Configuration Files

ExpOps projects use YAML configuration files to define project settings, pipeline structure, and execution parameters.

## Project Configuration

**Location**: `configs/project_config.yaml`

This is the main configuration file that defines:

### Metadata

- **Project name**: Identifier for the project
- **Description**: Project description
- **Version**: Project version

### Environment

Virtual environment settings with separate requirements for:
- **Training**: Dependencies for model training
- **Reporting**: Dependencies for chart generation

### Reproducibility

- **Random seed**: Configuration for reproducibility
- **Experiment tracking**: Settings for metrics and logging

### Model Configuration

- **Framework selection**: ML framework (sklearn, PyTorch, TensorFlow, etc.)
- **Custom script paths**: Paths to model implementation files
- **Hyperparameters**: Model-specific parameters

### Pipeline Definition

- **DAG structure**: `process_adjlist` defines the pipeline graph
- **Process definitions**: Individual process configurations with dependencies
- **Step dependencies**: Order of execution

### Reporting

- **Chart definitions**: Static and dynamic chart configurations
- **Probe paths**: Metrics extraction paths for charts

### Cache Backend

- **Backend type**: Local filesystem, GCS, or other backends
- **Cache settings**: Configuration for step-level caching

## Cluster Configuration

**Location**: `configs/cluster_config.yaml` (optional)

Defines settings for distributed execution:

### Provider

- **Cluster provider**: `slurm`, `dask`, or other providers

### Workers

- **Number of workers**: Worker node count
- **Resource allocation**: Cores and memory per worker

### Queue Settings

- **Job queue**: Queue name for job submission
- **Walltime**: Maximum execution time
- **Scheduler configuration**: Scheduler-specific settings

## Example Configuration

See the template projects for example configurations:
- `sklearn-basic`: Basic local execution setup
- `premier-league`: Comprehensive setup with cluster configuration

## Next Steps

- Learn about [Model Code](model-code.md) implementation
- Understand [Chart Generation](charts.md) configuration
- Explore [Advanced Topics](../advanced/cluster-config.md) for detailed configuration

