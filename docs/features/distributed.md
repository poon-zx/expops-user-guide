# Distributed Computing

ExpOps supports distributed execution on clusters and local multi-worker parallelism.

## Local Execution

Run pipelines locally with multi-worker parallelism:

```bash
expops run my-project --local
```

This uses local workers for parallel step execution.

## Cluster Execution

Execute pipelines on distributed clusters using Dask.

### SLURM Support

Run on SLURM clusters:

1. Install SLURM dependencies:
```bash
pip install expops[slurm]
```

2. Configure cluster in `configs/cluster_config.yaml`:
```yaml
provider: slurm
workers: 4
cores_per_worker: 2
memory_per_worker: 4GB
```

3. Run without `--local` flag:
```bash
expops run my-project
```

### Dask Cluster

Connect to existing Dask clusters or create new ones.

## Configuration

Cluster settings are defined in `configs/cluster_config.yaml`:

- **Provider**: `slurm`, `dask`, or other providers
- **Workers**: Number of worker nodes
- **Resources**: Cores and memory per worker
- **Queue settings**: Job queue and walltime

## Resource Management

ExpOps automatically:
- Allocates resources to workers
- Manages job submission
- Handles worker failures
- Distributes steps across workers

## Next Steps

- Learn about [Cluster Configuration](../advanced/cluster-config.md)
- Understand [Environment Isolation](environments.md)
- Explore [Caching & Reproducibility](caching.md)

