# ExpOps User Guide

Welcome to the ExpOps user guide! ExpOps is a project-based experiment runner that keeps each experiment isolated under a workspace, runs pipelines, and saves run artifacts with optional tracking/backends.

## What is ExpOps?

`expops` is a comprehensive MLOps platform designed to help you manage machine learning experiments efficiently. It provides:

- **Project-Based Workflow**: Each ML project is isolated in its own workspace with independent configurations, dependencies, and artifacts
- **DAG Pipeline Execution**: Define complex ML pipelines as directed acyclic graphs (DAGs) using NetworkX
- **Distributed Computing**: Execute pipelines on clusters using Dask (with SLURM support) or run locally
- **Environment Isolation**: Automatic virtual environment management (venv/conda)
- **Caching & Reproducibility**: Intelligent step-level caching with configurable backends
- **Static & Dynamic Reporting**: Generate static charts (PNG) and interactive dynamic charts

## Quick Start

Get started with ExpOps in minutes:

```bash
pip install expops
mkdir -p ~/expops-workspace && cd ~/expops-workspace
expops create sklearn-basic --template sklearn-basic
expops run sklearn-basic --local
```

## Documentation Structure

This guide is organized into the following sections:

- **[Getting Started](getting-started/installation.md)**: Installation and basic setup
- **[Project Structure](project-structure/overview.md)**: Understanding the project layout
- **[Features](features/capabilities.md)**: Detailed feature documentation
- **[Templates](templates/available-templates.md)**: Available project templates
- **[Web UI](web-ui/local-ui.md)**: Using the local web interface
- **[Advanced Topics](advanced/cluster-config.md)**: Advanced configuration and customization

## Installation

The installed CLI command is **`expops`** (alias: `expops-platform`).

```bash
pip install expops
```

## Next Steps

- Read the [Installation Guide](getting-started/installation.md) for detailed setup instructions
- Follow the [Quick Start](getting-started/quick-start.md) tutorial
- Learn about [Creating a Project](getting-started/creating-a-project.md)

