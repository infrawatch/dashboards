# Service Telemetry Driven Dashboards

Files in this directory are intended to be used with the [Service Telemetry
Framework](https://github.com/infrawatch) (STF). Installation of STF is
available at https://infrawatch.github.com/documentation.

## Dashboards for OpenStack

| filename | description |
--------------------------
| cloud-infra-dashboard.yaml  | Overall view of cloud infrastructure with a focus on CPU, memory, network, and disk health                                               |
| datasource.yaml             | Default Grafana datasources, compatible with a typical STF deployment                                                                    |
| grafana.yaml                | Grafana manifest to launch a Grafana instance via the Grafana Operator                                                                   |
| rhos-cloud-dashboard.yaml   | Development dashboard. Not complete.                                                                                                     |
| rhos-dashboard.yaml         | Individual node drill-down dashboard for cloud infrastructure with a focus on CPU, memory, network, and disk health                      |
| rhos-service-dashboard.yaml | Development dashboard. Not complete.                                                                                                     |
| subscription.yaml           | Subscription manifest for installation of the Grafana Operator via the Operator Lifecycle Manager from the OperatorHub.io catalog source |

# Additional notes

## cloud-infra-dashboard.yaml

Additional plugins are required for use of this dashboard from a typical
OpenStack deployment as recommended via the STF documentation. (This note
accurate as of 20 August 2020.)

In addition to the default recommended TripleO Heat Template environment file
(as documented at https://infrawatch.github.io/documentation/#configuring-red-hat-openstack-platform-overcloud-for-stf_completing-the-stf-configuration)
you will need to append to the `CollectdExtraPlugins` and `ExtraConfig`
parameters.

```
CollectdExtraPlugins:
  - <existing list items>
  - vmem

ExtraConfig:
  <existing parameters>
  collectd::plugin::vmem::verbose: true
```
