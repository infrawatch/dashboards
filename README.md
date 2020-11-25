# Service Telemetry Dashboards

Dashboards for use with Service Telemetry Framework. These dashboards can be
loaded into a Grafana instance connected to backend data sources exposed by the
Service Telemetry Framework.

## Installation

Deploying a Grafana instance requires the deployment of the Grafana Operator
first from the Community Operators catalog source. Then, run the following:

```bash
oc create -f deploy/subscription.yaml \
        -f deploy/grafana.yaml

# datasources
ES_PASSWORD=$(oc get secret elasticsearch-es-elastic-user \
-ogo-template='{{ .data.elastic | base64decode }}') && \
sed "s/ES_PASSWORD/$ES_PASSWORD/g" deploy/datasource.yaml | oc apply -f -

# dashboards
oc create -f deploy/rhos-dashboard.yaml \
        -f deploy/rhos-cloud-dashboard.yaml

# vm dashboard [WIP]
oc create -f contrib/vm-view.yaml
```
