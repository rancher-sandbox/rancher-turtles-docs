---
sidebar_position: 4
---

# Installing the CoreProvider

Any existing namespace could be utilized for providers in the Kubernetes cluster. However, before creating a provider object, make sure the specified namespace has been created. In the example below, we use the `capi-system` namespace. To create this namespace through either the Command Line Interface (CLI) by running `kubectl create namespace capi-system`, or the declarative approach described in the [official Kubernetes documentation](https://kubernetes.io/docs/tasks/administer-cluster/namespaces-walkthrough/#create-new-namespaces) could be used.

:::note
Only one CoreProvider can be installed at the same time on a single cluster.
:::

## Option 1: CAPIProvider resource

This section describes how to install the `CoreProvider` via `CAPIProvider`, which is responsible for managing the Cluster API CRDs and the Cluster API controller.

*Example:*

```yaml
apiVersion: turtles-capi.cattle.io/v1alpha1
kind: CAPIProvider
metadata:
  name: cluster-api
  namespace: capi-system
spec:
  version: v1.4.6
  type: core # required
```

## Option 2: CoreProvider resource

This section describes how to install the `CoreProvider`, which is responsible for managing the Cluster API CRDs and the Cluster API controller.

*Example:*

```yaml
apiVersion: operator.cluster.x-k8s.io/v1alpha2
kind: CoreProvider
metadata:
  name: cluster-api
  namespace: capi-system
spec:
  version: v1.4.6
```
