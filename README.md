# Generic App Helm Chart
<a href="https://github.com/small-hack/generic-app-helm/releases"><img src="https://img.shields.io/github/v/release/small-hack/generic-app-helm?style=plastic&labelColor=blue&color=green&logo=GitHub&logoColor=white"></a>

This is a helm chart for a generic Kubernetes Application.


### TLDR
```bash
helm repo add generic-app https://small-hack.github.io/generic-app-helm
helm install generic-app/generic-app --generate-name
```

## Why?

Because sometimes you don't want to write a whole helm chart for a simple app. The default chart generated with `helm create my-new-chart-name` is pretty good, but it's missing a couple of features. This chart can be used as a base chart for that docker container you have that you want on Kubernetes, but don't feel like writing a helm chart to make it accessible to others. Now you have no excuse :) Tip: Use this as a cheap way to get going with Argo CD Applications/ApplicationSets faster.

## How?

Because this chart is basically just the stock helm chart, you can use it like any other. It defaults to just deploying the nginx container, but you can change that. In fact, you can change basically everything. We even let you disable the default service, and have an option to deploy a Job instead of (or in addition to) a Deployment.


### Changing the default deployment

Here's how to get started using your own docker container

```yaml
deployment:
  image:
    # -- provide this only if you're not hosting on hub.docker.com (docker.io)
    registry: ""
    # -- this can be set to any docker repo
    repository: "mydockercontainer"
    # -- docker image tag to pull
    tag: "latest"
```

#### Disabling the deployment

Sometimes you just need a job...

```yaml
deployment:
  enabled: false
```


## Enabling a job

```yaml
job:
  enabled: true
  image:
    # -- provide this only if you're not hosting on hub.docker.com (docker.io)
    registry: ""
    # -- this can be set to any docker repo
    repository: "mydockercontainer"
    # -- docker image tag to pull
    tag: "latest"
```

### Enabling the ingress

```yaml
ingress:
  enabled: true
```

### Disabling the service

```yaml
service:
  enabled: false
```

## Status

Submit any PRs you may have and please feel free to submit issues if you have a generic feature :P
