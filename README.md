# airsonic-advanced Helm Chart
![Version: 0.2.0](https://img.shields.io/badge/Version-0.2.0-informational?style=flat-square)
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
| env.contextPath | string | `"/"` | URI path on tomcat |
| env.pgid | int | `1000` | group id for container user |
| env.puid | int | `1000` | user id for container |
| env.timezone | string | `"Etc/UTC"` | timezone, airsonic-advanced will use |
| image.pullPolicy | string | `"IfNotPresent"` | pull policy |
| image.repository | string | `"linuxserver/airsonic-advanced"` | repository with airsonic-advanced image |
| image.tag | string | `"11.0.0"` | current version of the image |
| imagePullSecrets | list | `[]` | imagePullSecrets (not needed, if default image is used) |
| ingress | object | `{"annotations":{},"className":"","enabled":false,"hosts":[{"host":"chart-example.local","paths":[{"path":"/","pathType":"ImplementationSpecific"}]}],"tls":[]}` | Configure ingress |
| nfsMounts.enabled | bool | `false` | enable mounting of nfs exports |
| nfsMounts.mounts[0] | object | `{"capacity":"20Gi","exportPath":"/music","mountPath":"/music","name":"music","nfsServer":"xxx.xxx.xxx.xxx","readOnly":false}` | name of mount |
| nfsMounts.mounts[0].capacity | string | `"20Gi"` | desired capacity (usually not needed for nfs) |
| nfsMounts.mounts[0].exportPath | string | `"/music"` | export path on nfs server |
| nfsMounts.mounts[0].mountPath | string | `"/music"` | mount path on container |
| nfsMounts.mounts[0].nfsServer | string | `"xxx.xxx.xxx.xxx"` | ip or dns of nfs server |
| nfsMounts.mounts[0].readOnly | bool | `false` | mark mount as readonly |
| persistence.accessMode | string | `"ReadWriteOnce"` | accessMode |
| persistence.enabled | bool | `false` | enable persistence when true |
| persistence.size | string | `"8Gi"` | default storage size |
| persistence.storageClass | string | `""` | actual storageClass |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` | add annotations to serviceAccount |
| serviceAccount.create | bool | `true` | enable serviceAccount |
| serviceAccount.name | string | `""` | name of the serviceAccount (will be generated if empty) |

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| pmoscode | <info@pmoscode.de> | <https://pmoscode.de> |

## Contributing

If you want to add features or bugfixes, please open an issue (either feature or bug) and provide also an unittest (https://github.com/helm-unittest/helm-unittest).
To make things easier, you can use Taskfile (https://taskfile.dev/) to get a small shortcut for some useful commands.

You also need to copy the ".env-template" file as ".env" and configure it for your needs.

The Taskfile itself needs this tools to run the tasks:
- https://github.com/helm/chart-releaser
- https://helm.sh/docs/intro/quickstart/
- https://github.com/mbenabda/helm-local-chart-version (install it outside an GIT repo!)
- https://github.com/norwoodj/helm-docs
- https://github.com/helm-unittest/helm-unittest/
- https://github.com/pawamoy/git-changelog
