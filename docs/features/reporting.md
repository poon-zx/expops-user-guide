# Reporting

ExpOps supports both static and dynamic reporting for experiment visualization.

## Static Charts

Generate PNG image files from pipeline metrics:

- **Location**: `charts/plot_metrics.py`
- **Output**: PNG files in `artifacts/charts/<run-id>/`
- **Access**: Via file system or web UI

### Features

- Matplotlib-based visualization
- Access to all logged metrics
- Combine data from multiple steps
- Customizable styling

## Dynamic Charts

Interactive, real-time visualizations:

- **Location**: `charts/plot_metrics.js`
- **Updates**: Real-time during execution
- **Access**: Web UI only

### Features

- Chart.js integration
- Live metric streaming
- Interactive exploration
- Multiple chart types

## Metrics Logging

Log metrics in model code:

```python
from mlops.core.custom_model_base import log_metric

log_metric("accuracy", 0.95)
log_metric("loss", 0.05, step=epoch)
```

## Web UI

View charts in the local web UI:

```bash
python -m expops.web.server
```

Open `http://127.0.0.1:8000` to:
- Browse projects and runs
- View static charts
- Interact with dynamic charts

## Chart Types

Supported chart types:
- Line charts (time series, training curves)
- Bar charts (metric comparisons)
- Scatter plots (correlations)
- Histograms (distributions)
- Custom visualizations

## Next Steps

- Learn about [Chart Generation](../project-structure/charts.md)
- Explore the [Web UI](../web-ui/local-ui.md)
- See template projects for examples

