# generic-app

![Version: 0.1.1](https://img.shields.io/badge/Version-0.1.1-informational?style=flat-square) ![Type: application](https://img.shields.io/badge/Type-application-informational?style=flat-square) ![AppVersion: 1.16.0](https://img.shields.io/badge/AppVersion-1.16.0-informational?style=flat-square)

A generic Helm chart for Kubernetes for when you have a docker container and don't want to write a helm chart

## Maintainers

| Name | Email | Url |
| ---- | ------ | --- |
| JesseBot |  | <https://github.com/jessebot> |
| cloudymax |  | <https://github.com/cloudymax> |

## Values

| Key | Type | Default | Description |
|-----|------|---------|-------------|
| deployment.affinity | object | `{}` | affinity settings for the deployment |
| deployment.autoscaling | object | `{"enabled":false,"maxReplicas":100,"minReplicas":1,"targetCPUUtilizationPercentage":80}` | autoscaling for the deployment |
| deployment.containerCommand | list | `[]` | command to pass to docker container |
| deployment.enabled | bool | `true` | enable the deployment vs job vs cronjob |
| deployment.env | list | `[]` | env list for deployment main container |
| deployment.envFrom | list | `[]` | env from list for deployment main container |
| deployment.image.pullPolicy | string | `"IfNotPresent"` | image pull policy, set to Always if using latest and it changes frequently |
| deployment.image.registry | string | `"docker.io"` | docker registry if not using docker.io |
| deployment.image.repository | string | `"nginx"` | docker repo |
| deployment.image.tag | string | `"latest"` | Overrides the image tag whose default is latest |
| deployment.imagePullSecrets | list | `[]` | optional image pull secrets |
| deployment.initcontainers | object | `{}` | extra init containers for the default deployment |
| deployment.livenessProbe | object | `{"enabled":true,"httpGet":{"path":"/","port":"http"}}` | livenessProbe for the deployment |
| deployment.nodeSelector | object | `{}` | node selector for deployment |
| deployment.podAnnotations | object | `{}` | extra pod annotations for the deployment |
| deployment.podLabels | object | `{}` | extra pod labels for the deployment |
| deployment.podSecurityContext | object | `{}` | pod securityContext deployment's main container |
| deployment.readinessProbe | object | `{"enabled":true,"httpGet":{"path":"/","port":"http"}}` | readinessProbe for the deployment |
| deployment.replicaCount | int | `1` | replica count if not using autoscaling |
| deployment.resources | object | `{}` | resources for the deployment |
| deployment.securityContext | object | `{}` | securityContext whole deployment |
| deployment.tolerations | list | `[]` | tolerations of taints on a node |
| deployment.volumeMounts | list | `[]` | Additional volumeMounts on the output Deployment definition. |
| deployment.volumes | list | `[]` | Additional volumes on the output Deployment definition. |
| fullnameOverride | string | `""` |  |
| ingress.annotations | object | `{}` |  |
| ingress.className | string | `""` |  |
| ingress.enabled | bool | `false` |  |
| ingress.hosts[0].host | string | `"chart-example.local"` |  |
| ingress.hosts[0].paths[0].path | string | `"/"` |  |
| ingress.hosts[0].paths[0].pathType | string | `"ImplementationSpecific"` |  |
| ingress.tls | list | `[]` |  |
| job.affinity | object | `{}` | affinity settings for the job |
| job.containerCommand | list | `[]` | command to pass to docker container |
| job.enabled | bool | `false` | enable a job |
| job.env | list | `[]` | env list for job main container |
| job.envFrom | list | `[]` | env from list for job main container |
| job.image.pullPolicy | string | `"IfNotPresent"` | image pull policy, set to Always if using latest and it changes frequently |
| job.image.registry | string | `"docker.io"` | docker registry if not using docker.io |
| job.image.repository | string | `"nginx"` | docker repo |
| job.image.tag | string | `"latest"` | Overrides the image tag whose default is latest |
| job.imagePullSecrets | list | `[]` | optional image pull secrets |
| job.initcontainers | object | `{}` | extra init containers for the default job |
| job.nodeSelector | object | `{}` | node selector for job |
| job.podAnnotations | object | `{}` | extra pod annotations for the job |
| job.podLabels | object | `{}` | extra pod labels for the job |
| job.podSecurityContext | object | `{}` | pod securityContext job's main container |
| job.replicaCount | int | `1` | replica count if not using autoscaling |
| job.resources | object | `{}` | resources for the job |
| job.restartPolicy | string | `"never"` | restart policy if the job fails; can be never, or always |
| job.securityContext | object | `{}` | securityContext whole job |
| job.tolerations | list | `[]` | tolerations of taints on a node |
| job.volumeMounts | list | `[]` | Additional volumeMounts on the output job definition. |
| job.volumes | list | `[]` | Additional volumes on the output job definition. |
| nameOverride | string | `""` |  |
| service.enabled | bool | `true` |  |
| service.port | int | `80` |  |
| service.type | string | `"ClusterIP"` |  |
| serviceAccount.annotations | object | `{}` |  |
| serviceAccount.automount | bool | `true` |  |
| serviceAccount.create | bool | `true` |  |
| serviceAccount.name | string | `""` |  |

----------------------------------------------
Autogenerated from chart metadata using [helm-docs v1.13.1](https://github.com/norwoodj/helm-docs/releases/v1.13.1)
