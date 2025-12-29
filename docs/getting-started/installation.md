# Installation

## Prerequisites

ExpOps requires Python 3.8 or higher.

## Install from PyPI

The simplest way to install ExpOps is using pip:

```bash
pip install expops
```

## Verify Installation

After installation, verify that the CLI is available:

```bash
expops --help
```

or

```bash
expops-platform --help
```

Both commands (`expops` and `expops-platform`) are aliases for the same CLI tool.

## Optional Dependencies

### SLURM Support

If you plan to use SLURM for cluster execution, install the optional dependencies:

```bash
pip install expops[slurm]
```

This installs `dask-jobqueue` for SLURM integration.

## Development Installation

To install ExpOps in development mode:

```bash
git clone https://github.com/yourusername/mlops-platform.git
cd mlops-platform
pip install -e .
```

## Next Steps

- Follow the [Quick Start](quick-start.md) guide to run your first experiment
- Learn about [Creating a Project](creating-a-project.md)

