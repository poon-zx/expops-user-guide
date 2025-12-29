# Available Templates

ExpOps provides pre-configured project templates to help you get started quickly.

## Using Templates

Create a project from a template:

```bash
expops create my-project --template <template-name>
```

## Template List

### sklearn-basic

A runnable project skeleton with:
- Basic sklearn model training
- Configuration files
- Data/models/charts structure
- Requirements files
- Example plots

**Use case**: Learning ExpOps, simple ML projects

**Features**:
- Minimal setup
- Local execution
- Static charts

### premier-league

A comprehensive ML project with:
- Football match prediction
- Cluster configuration
- Dynamic charts
- Complex pipeline

**Use case**: Production ML projects, distributed execution

**Features**:
- SLURM cluster config
- Dynamic real-time charts
- Multiple pipeline steps
- Advanced reporting

## Template Structure

All templates include:
- `configs/project_config.yaml`: Project configuration
- `models/`: Model implementation
- `charts/`: Chart generation code
- `requirements.txt`: Dependencies
- Example data structure

## Next Steps

- Learn about [sklearn-basic](sklearn-basic.md) template
- Explore [premier-league](premier-league.md) template
- Create your own [Custom Models](../advanced/custom-models.md)

