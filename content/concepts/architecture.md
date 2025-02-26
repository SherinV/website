---
title: Architecture
weight: -20
---

This page tells you the architecture and basic concepts in open-cluster-management.

<!-- spellchecker-disable -->

{{< toc >}}

<!-- spellchecker-enable -->

## Hub cluster

The _hub_ cluster is the common term that is used to define the central controller that runs in a Kubernetes cluster.
The hub cluster aggregates information from multiple clusters by using an asynchronous work request model.


## Klusterlet

The _klusterlet_ is an agent running on the cluster managed by the hub.


## Managed cluster

The _managed cluster_ provides a representation of the managed cluster on the hub. ManagedCluster controls the lifecycle of whether the remote cluster has been "accepted" by the Hub for management and can retrieve information from the Hub to direct a set of manifests or actions to apply.


## Application lifecycle

The _application lifecycle_ defines the processes that are used to manage application resources on your managed clusters.
A multi-cluster application uses a Kubernetes specification, but with additional automation of the deployment and lifecycle management of resources to individual clusters.
A multi-cluster application allows you to deploy resources on multiple clusters, while maintaining easy-to-reconcile service routes, as well as full control of Kubernetes resource updates for all aspects of the application.

## Cluster lifecycle (work in progress)

The _cluster lifecycle_ defines the process the lifecycle of a cluster on the hub side. It includes the create, destroy of cluster through [hive](https://github.com/openshift/hive), the attach and detach functionality, the addon lifecycle and a UI to give a better user experience on that process.

### Discovery (work in progress)

_Discovery_ defines the processes that are used to identify related clusters which are available for import from [Openshift Cluster Manager](https://cloud.redhat.com/openshift/). By aggregating cluster information, _Discovery_ enables the user to quickly get started importing clusters to the hub. An unmanaged cluster available for import is defined as a DiscoveredCluster. A DiscoveryConfig resource must be created to enable _Discovery_. The DiscoveryConfig contains the information and filters necessary to identify DiscoveredClusters. A DiscoveredCluster resource can be imported into the _hub cluster_ at which point it becomes a ManagedCluster. For more information see the [Discovery repo](https://github.com/open-cluster-management/discovery).

### Application console (work in progress)

The _Application console_ defines the user interface used to create and manage application resources deployed on your managed clusters through the use of _Application lifecycle_ subscription operators.

## Governance and risk (work in progress)

_Governance and risk_ is the term used to define the processes that are used to manage security and compliance from the hub cluster. Ensure the security of your cluster with the extensible policy framework. After you configure a hub cluster and a managed cluster, you can create, modify and delete policies on the hub and apply policies to managed clusters.

## Multiclusterhub Operator (work in progress)

### Multiclusterhub Repo (work in progress)

_Multiclusterhub Repo_ is the term used to define the internal helm repository used during installation, upgrade, and uninstall of related multiclusterhub components. 
