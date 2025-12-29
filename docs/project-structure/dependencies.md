# Dependencies

ExpOps projects use separate dependency files for different components.

## Main Dependencies

**Location**: `requirements.txt`

Contains dependencies for training and inference:

- **Core ML libraries**: scikit-learn, XGBoost, PyTorch, TensorFlow, etc.
- **Data processing**: pandas, numpy
- **Other dependencies**: Any libraries needed for model execution

### Example

```txt
pandas>=1.5.0
numpy>=1.20.0
scikit-learn>=1.0.0
```

## Chart Dependencies

**Location**: `charts/requirements.txt`

Contains dependencies only for chart generation:

- **Visualization libraries**: matplotlib, seaborn
- **Minimal dependencies**: Kept separate to reduce overhead in training environments

### Example

```txt
matplotlib>=3.5.0
seaborn>=0.12.0
```

## Environment Isolation

ExpOps automatically manages separate virtual environments:
- **Training environment**: Uses `requirements.txt`
- **Reporting environment**: Uses `charts/requirements.txt`

This separation:
- Reduces training environment size
- Allows different Python versions if needed
- Isolates visualization dependencies

## Installation

Dependencies are automatically installed when:
- Creating a project from template
- Running a project for the first time
- Environment is missing or outdated

## Next Steps

- Learn about [Environment Isolation](../features/environments.md)
- Understand [Project Structure](overview.md)
- Explore [Configuration Files](configuration.md)

