# Chart Generation

ExpOps supports both static and dynamic chart generation for visualizing experiment results.

## Static Charts

**Location**: `charts/plot_metrics.py`

Static charts generate PNG image files that are saved to disk.

### Chart Functions

Functions decorated with `@chart()` generate visualizations:

```python
from mlops.reporting.registry import chart
from mlops.reporting.context import ChartContext

@chart()
def plot_metrics(context: ChartContext):
    # Access metrics from previous steps
    metrics = context.get_metrics()
    
    # Generate matplotlib plot
    import matplotlib.pyplot as plt
    plt.figure()
    # ... plotting code ...
    plt.savefig("output.png")
```

### Metrics Access

Charts can read metrics from previous pipeline steps via `ChartContext`:
- Access logged metrics
- Read step outputs
- Combine data from multiple steps

### Output

Static charts produce image files (PNG) saved to:
```
artifacts/charts/<run-id>/
```

## Dynamic Charts

**Location**: `charts/plot_metrics.js`

Dynamic charts provide real-time, interactive visualizations.

### Features

- **Real-time updates**: Charts update as metrics are logged during execution
- **Chart.js integration**: Uses Chart.js library for interactive visualizations
- **Live metrics**: Subscribes to metric streams from multiple pipeline steps
- **Web UI integration**: Rendered in the web UI for interactive exploration

### Example

```javascript
// Subscribe to metrics
subscribeToMetrics((metrics) => {
    // Update Chart.js chart
    chart.data.datasets[0].data = metrics;
    chart.update();
});
```

## Chart Dependencies

**Location**: `charts/requirements.txt`

Separate dependencies for chart generation:
- Visualization libraries (matplotlib, seaborn)
- Minimal dependencies to reduce training environment overhead

## Viewing Charts

### Static Charts

Static charts are saved as PNG files and can be:
- Viewed in the file system
- Displayed in the web UI

### Dynamic Charts

Dynamic charts are available in the web UI:
- Real-time updates during execution
- Interactive exploration
- Multiple chart types

## Next Steps

- Learn about the [Web UI](../web-ui/local-ui.md)
- Explore [Reporting Features](../features/reporting.md)
- See template projects for chart examples

