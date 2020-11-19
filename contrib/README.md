# Additional Dashboards

The `contrib/` directory contains additional Grafana compatible dashboards that
can be imported directly in to existing Grafana environments.

These dashboards are intended to be used with Service Telemetry Framework
(https://github.com/infrawatch) but for various reasons have not been brought
into the core project (still in development, not yet automated for use with the
Grafana Operator, not generic enough for various environments, etc).

Files in yaml format can be deployed to the grafana operator in STF with
`oc apply -f <name>.yaml`
