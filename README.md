# strongDM Helm Charts

This repo contains packaged Helm charts that I helped design for strongDM:

* [strongDM Relay/Gateway](#strongdm-relaygateway)

* [strongDM Client Container](#strongdm-client-container)

## [strongDM Relay/Gateway](deployments/sdm-relay)

This is a deployment of the strongDM Relay/Gateway into Kubernetes using Helm.
### Prerequisites

* A Kubernetes Cluster v1.16+

* Helm 3.0+

* Git

* If you are going to use [Nginx Ingress Controller](https://kubernetes.github.io/ingress-nginx/), then you will need to manually patch your [services to allow TCP and UDP traffic](https://kubernetes.github.io/ingress-nginx/user-guide/exposing-tcp-udp-services/)

* [A strongDM Gateway/Relay Token](https://www.strongdm.com/docs/admin-ui-guide/network/gateways)

### Installing the Chart

```shell
helm repo add strongdm https://helm.strongdm.com/stable/
helm install [RELEASE_NAME] strongdm/sdm-relay -f values.yaml
helm status [RELEASE_NAME]
```

_See [configuration](deployments/sdm-relay/README.md#configuration) options._

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

### Upgrading the Chart

```shell
helm upgrade [RELEASE_NAME] strongdm/sdm-relay --install
```

_See [helm upgrade](https://helm.sh/docs/helm/helm_upgrade/) for command documentation._

### Uninstalling the Chart

```shell
helm uninstall [RELEASE_NAME]
```

The command removes all the Kubernetes components associated with the release and deletes the release.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._

## [strongDM Client Container](deployments/sdm-client)

This repo provides an implementation of a strongDM Client Container inside Kubernetes using Helm.

[Learn more about deploying strongDM's cliet container inside Kubernetes on their docs site.](https://www.strongdm.com/docs/automation/containers/client-container)

### Prerequisites

* A Kubernetes Cluster v1.16+

* Helm 3.0+

* Git

* If you are going to use [Nginx Ingress Controller](https://kubernetes.github.io/ingress-nginx/), then you will need to manually patch your [services to allow TCP and UDP traffic](https://kubernetes.github.io/ingress-nginx/user-guide/exposing-tcp-udp-services/)

* [A strongDM Service Token](https://www.strongdm.com/docs/admin-ui-guide/access/service-accounts)

_**Note: In order to get a Gateway Token you'll need an external address to register. This is external address is immutable after creation.**_

### Installing the Chart

```shell
helm repo add strongdm https://helm.strongdm.com/stable/
helm install [RELEASE_NAME] strongdm/sdm-client -f values.yaml
helm status [RELEASE_NAME]
```

_See [configuration](deployments/sdm-client/README.md#configuration) options._

_See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation._

### Upgrading the Chart

```shell
helm upgrade [RELEASE_NAME] strongdm/sdm-client --install
```

_See [helm upgrade](https://helm.sh/docs/helm/helm_upgrade/) for command documentation._

### Uninstalling the Chart

```shell
helm uninstall [RELEASE_NAME]
```

The command removes all the Kubernetes components associated with the release and deletes the release.

_See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation._
