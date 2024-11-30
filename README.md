# az-logs

Our aim is to collect Docker `Custom json logs` from Ubuntu `IoT Edge devices` with a number of Docker containers.
Currently we achieve this with a `OMS-Agent` container.
We want to use `Otel Collector` instead, to ingest the logs into a Log Analytics Workspace `Custom table`. The custom table to be in a `Basic Plan`.

## Status

* A log analytics workspace with a `DCR-based` custom log table. Transformed from a docker log file, typically found in /var/lib/docker/containers/

![Project Logo](images/basic-log-table.png)

* 

## Creating a data collection rule with add a Custom JSON Log

The three methods to create a data collection rule with `Custom JSON Logs`:

* Using Azure Portal
* Using ARM template
* Using Azure CLI  

### 1. Azure Portal

We were able to create a Data Collection Rule with Performance Counter. The `Azure Monitor Agent`, deployed on our IoT Edge devices,  are successfully ingesting the linux host metrics in the `Perf` table of the Log Analytics Workspace.

![Performance Counters](images/az-monitor-data-collection-rule-performance-counters.png)

When we attempt to add `Custom JSON Logs` as an additional Data Source, this warning appears:
`'Custom JSON log' data source configuration is currently unavailable through the Portal as it is undergoing design updates to accommodate recent changes. For now, please use Azure CLI to configure 'Custom JSON log' in Data Collection Rules. Learn more.`

![Performance Counters](images/az-monitor-data-collection-rule-custom-json-logs.png)

### 2. ARM template

