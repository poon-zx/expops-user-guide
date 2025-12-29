# Platform Capabilities

ExpOps provides a comprehensive MLOps platform with the following key features:

## Project-Based Workflow

Each ML project is isolated in its own workspace with:
- Independent configurations
- Separate dependencies
- Isolated artifacts
- Independent versioning

## DAG Pipeline Execution

Define complex ML pipelines as directed acyclic graphs (DAGs):
- **NetworkX-based**: Uses NetworkX for graph representation
- **Parallel execution**: Run independent steps in parallel
- **Conditional logic**: Support for conditional execution
- **Loops**: Iterative pipeline execution

See [DAG Pipeline Execution](pipelines.md) for details.

## Distributed Computing

Execute pipelines on clusters or locally:
- **Dask integration**: Distributed execution with Dask
- **SLURM support**: Run on SLURM clusters
- **Local parallelism**: Multi-worker execution on local machine

See [Distributed Computing](distributed.md) for details.

## Environment Isolation

Automatic virtual environment management:
- **venv/conda support**: Choose your environment manager
- **Separate environments**: Training and reporting environments
- **Automatic setup**: Environments created and managed automatically

See [Environment Isolation](environments.md) for details.

## Caching & Reproducibility

Intelligent step-level caching:
- **Configurable backends**: Local filesystem, GCS, or custom backends
- **Reproducibility guarantees**: Random seed management
- **Step-level caching**: Cache individual pipeline steps

See [Caching & Reproducibility](caching.md) for details.

## Static & Dynamic Reporting

Generate visualizations:
- **Static charts**: PNG image files
- **Dynamic charts**: Interactive real-time visualizations
- **Web UI**: Browse and interact with charts

See [Reporting](reporting.md) for details.

## Next Steps

- Explore individual features in detail
- Learn about [Creating a Project](../getting-started/creating-a-project.md)
- Check out [Templates](../templates/available-templates.md)

