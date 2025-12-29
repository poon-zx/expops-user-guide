# Custom Models

Create custom model implementations for your ExpOps projects.

## Model File Structure

**Location**: `models/<model_name>.py`

## Decorators

### @process()

Define a process (pipeline step):

```python
from mlops.core.custom_model_base import process

@process()
def my_process():
    # Process logic
    pass
```

### @step()

Define a step function:

```python
from mlops.core.custom_model_base import step

@step()
def my_step():
    # Step logic
    return result
```

### Dependencies

Steps can depend on other steps:

```python
@step(depends_on=["step1", "step2"])
def step3(result1, result2):
    # Combine results
    return combined
```

## Metrics Logging

Log metrics for tracking:

```python
from mlops.core.custom_model_base import log_metric

log_metric("accuracy", 0.95)
log_metric("loss", 0.05, step=epoch)
```

## Data Flow

Steps receive outputs from dependencies:

```python
@step()
def load_data():
    return {"data": data}

@step(depends_on=["load_data"])
def process(data_dict):
    data = data_dict["data"]
    # Process data
    return processed
```

## Best Practices

1. **Idempotent steps**: Steps should produce same output for same inputs
2. **Clear dependencies**: Explicitly define step dependencies
3. **Log metrics**: Use `log_metric()` for important values
4. **Error handling**: Handle errors gracefully
5. **Documentation**: Document step purposes and inputs/outputs

## Examples

See template projects for examples:
- `sklearn-basic`: Simple sklearn pipeline
- `premier-league`: Complex multi-step pipeline

## Next Steps

- Learn about [Model Code](../project-structure/model-code.md)
- Understand [Pipeline Execution](../features/pipelines.md)
- Explore [Configuration Files](../project-structure/configuration.md)

