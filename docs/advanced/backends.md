# Backends

ExpOps supports multiple backends for caching and storage.

## Cache Backends

### Local Filesystem

Default backend for local development:

```yaml
model:
  parameters:
    cache:
      backend: local
```

**Features**:
- Fast access
- No external dependencies
- Limited to single machine
- No web UI metrics support

### Google Cloud Storage (GCS)

Remote backend for shared caching:

```yaml
model:
  parameters:
    cache:
      backend: gcs
      bucket: my-bucket
```

**Features**:
- Cross-machine sharing
- Persistent storage
- Web UI support
- Requires GCP credentials

**Setup**:
1. Create GCS bucket
2. Set up credentials in `keys/`
3. Configure bucket name in config

### Custom Backends

Implement custom backends for other storage systems.

## KV Backends

Key-value backends for metrics and metadata:

### Firestore

Google Cloud Firestore:

```yaml
model:
  parameters:
    cache:
      backend: gcs
      kv_backend: firestore
```

**Setup**:
1. Create Firestore database
2. Add credentials to `keys/firestore.json`
3. Configure in project config

## Configuration

Backend settings in `configs/project_config.yaml`:

```yaml
model:
  parameters:
    cache:
      backend: gcs  # or local, custom
      bucket: my-bucket  # for GCS
      kv_backend: firestore  # optional
```

## Web UI Requirements

For web UI metrics and charts:
- Use remote backend (GCS, etc.)
- Configure KV backend for metrics
- Ensure credentials are set up

## Next Steps

- Learn about [Caching & Reproducibility](../features/caching.md)
- Understand [Configuration Files](../project-structure/configuration.md)
- Explore [Web UI](../web-ui/local-ui.md)

