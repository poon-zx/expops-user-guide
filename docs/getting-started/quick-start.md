# Quick Start

This guide will help you get started with ExpOps using the built-in template.

## Step 1: Create a Workspace

First, create a workspace directory for your ExpOps projects:

```bash
mkdir -p ~/expops-workspace && cd ~/expops-workspace
```

## Step 2: Create a Project from Template

Use the `sklearn-basic` template to create your first project:

```bash
expops create sklearn-basic --template sklearn-basic
```

This creates a new project at `projects/sklearn-basic/` with:
- Configuration files
- Model code
- Chart generation scripts
- Requirements files
- Example data structure

## Step 3: Run the Project

Run the project locally:

```bash
expops run sklearn-basic --local
```

This will:
1. Set up the virtual environment
2. Install dependencies
3. Execute the pipeline
4. Generate artifacts and charts

## Step 4: View Results

The project configuration is located at:
```
projects/sklearn-basic/configs/project_config.yaml
```

By default, the template uses a **local-first cache backend**. To enable cross-process live metrics (web UI) or remote backends, update `model.parameters.cache.backend` in the project config.

## Running on a Cluster

To run on a distributed cluster (e.g., SLURM):

1. Add a `cluster_config.yaml` under `configs/`
2. Remove the `--local` flag when running:

```bash
expops run sklearn-basic
```

## Next Steps

- Learn about [Creating a Project](creating-a-project.md) from scratch
- Explore the [Project Structure](../project-structure/overview.md)
- Check out available [Templates](../templates/available-templates.md)

