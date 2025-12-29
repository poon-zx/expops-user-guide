# Cluster Configuration

Configure ExpOps to run pipelines on distributed clusters.

## Cluster Providers

### SLURM

SLURM cluster support via `dask-jobqueue`:

```yaml
provider: slurm
workers: 4
cores_per_worker: 2
memory_per_worker: 4GB
queue: normal
walltime: "02:00:00"
```

### Dask

Connect to existing Dask clusters or create new ones.

## Configuration File

**Location**: `configs/cluster_config.yaml`

### Basic Settings

```yaml
provider: slurm
workers: 4
```

### Resource Allocation

```yaml
cores_per_worker: 2
memory_per_worker: 4GB
```

### Queue Settings

```yaml
queue: normal
walltime: "02:00:00"
```

### Scheduler Configuration

```yaml
scheduler:
  # Scheduler-specific settings
```

## Installation

For SLURM support:

```bash
pip install expops[slurm]
```

## Running on Cluster

Remove the `--local` flag:

```bash
expops run my-project
```

ExpOps will:
1. Read `cluster_config.yaml`
2. Submit jobs to the cluster
3. Distribute steps across workers
4. Collect results

## Local vs. Cluster

- **Local**: `expops run my-project --local` (uses local workers)
- **Cluster**: `expops run my-project` (uses cluster configuration)

## Next Steps

- Learn about [Distributed Computing](../features/distributed.md)
- Explore [Configuration Files](../project-structure/configuration.md)
- Understand [Backends](backends.md)

