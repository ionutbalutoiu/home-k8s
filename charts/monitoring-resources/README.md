# Monitoring Resources

This chart provides a set of resources that can be used to monitor the services deployed in the cluster.

## Kubernetes Mixin

The `files/k8s_alerts.yaml` and `files/k8s_rules.yaml` files are based on the [Grafana Kubernetes Mixin](https://github.com/grafana/kubernetes-mixin).

These can be updated by running the following commands:

```bash
# Clone the Grafana Kubernetes Mixin repository
git clone https://github.com/grafana/kubernetes-mixin.git
cd kubernetes-mixin

# Build the alerts and rules files
make prometheus_alerts.yaml
make prometheus_rules.yaml

# Copy the files to the chart
cp prometheus_alerts.yaml PATH_TO_CHART/files/k8s_alerts.yaml
cp prometheus_rules.yaml PATH_TO_CHART/files/k8s_rules.yaml
```

NOTE: These needs to be updated with the Grafana Alloy job labels (inspect git diff for changes).
