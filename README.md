# airsonic-advanced Helm Chart
![Version: 0.1.1](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square)
[![Artifact Hub](https://img.shields.io/endpoint?url=https://artifacthub.io/badge/repository/airsonic-advanced)](https://artifacthub.io/packages/search?repo=airsonic-advanced)

From https://github.com/airsonic-advanced/airsonic-advanced:
> Airsonic-Advanced is a more modern implementation of the Airsonic fork with several key performance and feature enhancements. It adds and supersedes several features in Airsonic.

> Airsonic is a free, web-based media streamer, providing ubiquitous access to your music. Use it to share your music with friends, or to listen to your own music while at work. You can stream to multiple players simultaneously, for instance to one player in your kitchen and another in your living room.

## Get Repo Info

    helm repo add my-airsonic-advanced https://pmoscode-helm.github.io/airsonic-advanced/
    helm repo update

## Install chart

    helm install [RELEASE_NAME] my-gotify/gotify

The command deploys airsonic-advanced on the Kubernetes cluster in the default configuration.

See configuration below.

See [helm install](https://helm.sh/docs/helm/helm_install/) for command documentation.

## Uninstall Chart

    helm uninstall [RELEASE_NAME]

This removes all the Kubernetes components associated with the chart and deletes the release.

See [helm uninstall](https://helm.sh/docs/helm/helm_uninstall/) for command documentation.

## Upgrading Chart

    helm upgrade [RELEASE_NAME] [CHART] --install

See [helm upgrade](https://helm.sh/docs/helm/helm_upgrade/) for command documentation.

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| affinity | object | `{}` |  |
| env.contextPath | string | `"/"` |  |
| env.pgid | int | `1000` |  |
| env.puid | int | `1000` |  |
| env.timezone | string | `"Etc/UTC"` |  |
| fullnameOverride | string | `""` |  |
| image.pullPolicy | string | `"IfNotPresent"` |  |
| image.repository | string | `"linuxserver/airsonic-advanced"` |  |
| image.tag | string | `"11.0.0"` |  |
| imagePullSecrets | list | `[]` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| nameOverride | string | `""` |  |
| nfsMounts.enabled | bool | `false` |  |
| nfsMounts.mounts[0].capacity | string | `"20Gi"` |  |
| nfsMounts.mounts[0].exportPath | string | `"/music"` |  |
| nfsMounts.mounts[0].mountPath | string | `"/music"` |  |
| nfsMounts.mounts[0].name | string | `"music"` |  |
| nfsMounts.mounts[0].nfsServer | string | `"xxx.xxx.xxx.xxx"` |  |
| nfsMounts.mounts[0].readOnly | bool | `false` |  |
| nodeSelector | object | `{}` |  |
| persistence.accessMode | string | `"ReadWriteOnce"` |  |
| persistence.enabled | bool | `false` |  |
| persistence.size | string | `"8Gi"` |  |
| persistence.storageClass | string | `""` |  |
| podAnnotations | object | `{}` |  |
| podSecurityContext | object | `{}` |  |
| resources | object | `{}` |  |
| securityContext | object | `{}` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |
| tolerations | list | `[]` |  |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| pmoscode | <info@pmoscode.de> | <https://pmoscode.de> |
