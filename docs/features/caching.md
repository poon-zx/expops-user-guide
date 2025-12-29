# Caching & Reproducibility

ExpOps provides intelligent step-level caching and reproducibility guarantees.

## Step-Level Caching

Each pipeline step can be cached independently:
- **Cache key**: Based on step inputs and code hash
- **Cache lookup**: Automatic before step execution
- **Cache storage**: Configurable backends

## Cache Backends

### Local Filesystem

Default backend for local development:
- Fast access
- No external dependencies
- Limited to single machine

### Google Cloud Storage (GCS)

Remote backend for shared caching:
- Cross-machine sharing
- Persistent storage
- Requires GCP credentials

### Custom Backends

Implement custom backends for other storage systems.

## Configuration

Cache settings in `configs/project_config.yaml`:

```yaml
model:
  parameters:
    cache:
      backend: local  # or gcs, custom
      enabled: true
```

## Reproducibility

### Random Seed Management

ExpOps manages random seeds for:
- NumPy random number generation
- Python's random module
- ML framework random states (sklearn, PyTorch, TensorFlow)

### Configuration

Seed settings in `configs/project_config.yaml`:

```yaml
reproducibility:
  seed: 42
  seed_all: true
```

## Cache Invalidation

Caches are invalidated when:
- Step code changes (detected via hash)
- Step inputs change
- Cache is manually cleared

## Benefits

Caching and reproducibility provide:
- **Faster iterations**: Skip unchanged steps
- **Reproducible results**: Same inputs produce same outputs
- **Cost savings**: Avoid redundant computation
- **Debugging**: Easier to isolate issues

## Next Steps

- Learn about [Backends](../advanced/backends.md)
- Understand [Pipeline Execution](pipelines.md)
- Explore [Configuration Files](../project-structure/configuration.md)

