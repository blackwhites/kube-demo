## Metrics with prometheus

## Exercise

This exercise takes the user through the process of install prometheus-operator into a cluster and demonstrates how to access the Prometheus dashboard to view metrics from the example application.

Prometheus-operator creates, configures and manages Prometheus monitoring instances.

The example application is a simple HTTP Server with predefined endpoints, there is also a small client which loops through the endpoints.

## Prereqs

This exercise makes the following assumptions

1. The user has administrative access to a running cluster

## Tasks

1. Install prometheus-operator

2. Install the example-app

3. Create a Prometheus instance to monitor the example-app using the packaged prometheus.yaml

4. Inspect the prometheus service to discover the external service IP & Port

5. Browse to the Prometheus dashboard and review the available metrics


# Useful links

[Prometheus.io](https://prometheus.io)

[Prometheus Operator](https://coreos.com/operators/prometheus/docs/latest/user-guides/getting-started.html)
