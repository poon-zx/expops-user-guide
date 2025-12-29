# DAG Pipeline Execution

ExpOps uses NetworkX to represent and execute ML pipelines as directed acyclic graphs (DAGs).

## Pipeline Definition

Pipelines are defined in `configs/project_config.yaml` using the `process_adjlist` format:

```yaml
process_adjlist:
  - [step1, step2]
  - [step2, step3]
  - [step1, step4]
```

This creates a DAG where:
- `step1` runs first
- `step2` depends on `step1`
- `step3` depends on `step2`
- `step4` depends on `step1` (runs in parallel with `step2`)

## Process Definitions

Processes are defined in model code using the `@process()` decorator:

```python
@process()
def my_process():
    # Process logic
    pass
```

## Step Functions

Steps are defined with the `@step()` decorator:

```python
@step()
def load_data():
    return data

@step(depends_on=["load_data"])
def preprocess(data):
    return processed_data
```

## Parallel Execution

Independent steps can run in parallel:

```yaml
process_adjlist:
  - [step1, step2]
  - [step1, step3]  # step2 and step3 run in parallel
```

## Conditional Logic

Pipelines support conditional execution based on step outputs or configuration.

## Loops

Iterative execution is supported for training loops and hyperparameter search.

## Execution Order

ExpOps automatically determines execution order based on:
- DAG structure
- Step dependencies
- Available resources

## Next Steps

- Learn about [Distributed Computing](distributed.md)
- Understand [Caching & Reproducibility](caching.md)
- Explore [Model Code](../project-structure/model-code.md)

