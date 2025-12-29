# Creating a Project

You can create a new ExpOps project either from scratch or using a template.

## Create from Template

Templates provide a pre-configured project structure with example code:

```bash
expops create my-project --template sklearn-basic
```

Available templates:
- `sklearn-basic`: Runnable project skeleton with a tiny sklearn model
- `premier-league`: Comprehensive ML project with cluster config and dynamic charts

See the [Templates](../templates/available-templates.md) section for more details.

## Create from Scratch

To create a new project without a template:

```bash
expops create my-project
```

This creates a minimal project structure that you can customize.

## Project Structure

After creation, your project will have the following structure:

```
my-project/
├── configs/
│   └── project_config.yaml
├── models/
├── charts/
├── data/
├── requirements.txt
└── ...
```

## Next Steps

- Learn about [Project Structure](../project-structure/overview.md) in detail
- Configure your [Project Configuration](../project-structure/configuration.md)
- Write your [Model Code](../project-structure/model-code.md)

