# Service Telemetry Dashboards

Dashboards for use with Service Telemetry Framework. These dashboards can be
loaded into a Grafana instance connected to backend data sources exposed by the
Service Telemetry Framework.

## Installation

Deploying a Grafana instance requires the deployment of the Grafana Operator
first from the Community Operators catalog source, followed by the following
commands.

```
oc create -f deploy/subscription.yaml \
    -f deploy/datasource.yaml \
    -f deploy/rhos-dashboard.yaml \
    -f deploy/grafana.yaml
```
