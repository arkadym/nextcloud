# nextcloud

[nextcloud](https://nextcloud.com/) is a file sharing server that puts the control and security of your own data back into your hands.

## TL;DR;

```console
helm repo add github-arkadym https://arkadym.github.io/helm
helm install my-release github-arkadym/nextcloud
```

## Introduction

This chart bootstraps an [nextcloud](https://hub.docker.com/_/nextcloud/) deployment on a [Kubernetes](http://kubernetes.io) cluster using the [Helm](https://helm.sh) package manager.

It also packages the:

* [Bitnami MariaDB chart](https://github.com/kubernetes/charts/tree/master/stable/mariadb) which is required for bootstrapping a MariaDB deployment for the database requirements of the nextcloud application.
* [Redis](http://redis.io/) which is require for memcached value.
* [Only Office](https://github.com/arkadym/onlyoffice) which is optional and required for document editing.
* [Elastic Search](https://github.com/arkadym/elasticsearch) which is optional and required for document full text search.
* [Kube Backup](https://github.com/arkadym/kube-backup) which is optional and required for backup, there are 3 backups required: DB, Nextcloud config and Nextcloud files

## Prerequisites

- Kubernetes 1.9+ with Beta APIs enabled
- PV provisioner support in the underlying infrastructure

## Installing the Chart

To install the chart with the release name `my-release`:

```console
helm repo add github-arkadym https://arkadym.github.io/helm
helm install my-release github-arkadym/nextcloud
```

The command deploys nextcloud on the Kubernetes cluster in the default configuration. The [configuration](#configuration) section lists the parameters that can be configured during installation.

> **Tip**: List all releases using `helm list`

## Uninstalling the Chart

To uninstall/delete the `my-release` deployment:

```console
helm delete my-release
```

The command removes all the Kubernetes components associated with the chart and deletes the release.

## Configuration
