# Service Telemetry Dashboards

Dashboards for use with Service Telemetry Framework. These dashboards can be
loaded into a Grafana instance connected to backend data sources exposed by the
Service Telemetry Framework.

## Installation

Deploying a Grafana instance requires the deployment of the Grafana Operator
from the Community Operators catalog source.

```bash
oc create -f deploy/subscription.yaml
```

Edit your ServiceTelemetry object to enable graphing by adding the following to
the CustomResource:

```yaml
...
  graphing:
    enabled: true
    grafana:
      ingressEnabled: true
...
```

Load the dashboard objects for Grafana:

```bash
oc create -f deploy/stf-1/rhos-dashboard.yaml \
          -f deploy/stf-1/rhos-cloud-dashboard.yaml \
          -f deploy/stf-1/virtual-machine-view.yaml \
          -f deploy/stf-1/memcached-dashboard.yml
```
