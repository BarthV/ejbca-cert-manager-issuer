# v1.3.2

## Features
* feat(helm): Rename `secureMetrics` to `metrics` and add `metrics.secure` and `metrics.metricsAddress` as configuration values. This way, Prometheus can scrape the controller manager metrics without the secure metrics proxy.
* feat(helm): Add configuration element in Helm chart default values file to configure container ports on the controller manager container.

## Fixes
* fix(deps): Update golang.org/x/net to v0.19.0
* fix(dockerfile): Upgrade builder image to golang:1.20 to address [CVE-2023-38408](https://scout.docker.com/vulnerabilities/id/CVE-2023-38408?utm_source=hub&utm_medium=ExternalLink&_gl=1*hbs4zp*_ga*MTU5MTQ4Mzk3MC4xNjkxNDI2NjAy*_ga_XJWPQMJYHQ*MTcwMzE4NzcyNC4xMDEuMS4xNzAzMTg4OTUxLjM3LjAuMA..)

# v1.3.1

## Features
* feat(controller): Implement Kubernetes `client-go` REST client for Secret/ConfigMap retrieval to bypass `controller-runtime` caching system. This enables the reconciler to retrieve Secret and ConfigMap resources at the namespace scope with only namespace-level permissions.
* feat(ci): Add GitHub Actions workflows to run unit tests and release container images when appropriate
* feat(helm): Create Helm chart to deploy the controller to a Kubernetes or OpenShift cluster

## Fixes
* fix(controller): Add logic to read secret from reconciler namespace or Issuer namespace depending on Helm configuration.