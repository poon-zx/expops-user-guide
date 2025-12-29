# Model Code

Model code in ExpOps projects defines the ML pipeline using decorators and functions.

## File Location

**Location**: `models/<model_name>.py`

## Key Components

### Process Definitions

Functions decorated with `@process()` define pipeline steps:

```python
from mlops.core.custom_model_base import process

@process()
def my_process():
    # Process logic
    pass
```

### Step Functions

Functions decorated with `@step()` perform specific operations:

```python
from mlops.core.custom_model_base import step

@step()
def load_data():
    # Data loading logic
    return data

@step()
def preprocess(data):
    # Preprocessing logic
    return processed_data

@step()
def train(data):
    # Training logic
    return model
```

### Pipeline Logic

Model files contain:
- **Data transformations**: Loading, cleaning, feature engineering
- **Model training**: Training ML models
- **Evaluation**: Model evaluation and metrics
- **Ensemble methods**: Combining multiple models

### Metrics Logging

Use `log_metric()` for experiment tracking:

```python
from mlops.core.custom_model_base import log_metric

log_metric("accuracy", 0.95)
log_metric("loss", 0.05)
```

## Dependencies Between Steps

Steps can depend on outputs from other steps:

```python
@step()
def step1():
    return result1

@step(depends_on=["step1"])
def step2(result1):
    # Use result1
    return result2
```

## Example

See template projects for complete examples:
- `sklearn-basic`: Simple sklearn pipeline
- `premier-league`: Complex pipeline with multiple steps

## Next Steps

- Learn about [Chart Generation](charts.md)
- Understand [Pipeline Execution](../features/pipelines.md)
- Explore [Advanced Topics](../advanced/custom-models.md)

