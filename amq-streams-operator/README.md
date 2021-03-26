# AMQ Streams Operator

Installs the AMQ Streams operator into all namespaces.

Current channel overlays include:
* [amq-streams-1.x](overlays/1.x)
* [amq-streams-1.6.x](overlays/1.6.x)
* [stable](overlays/stable)

## Usage

If you have cloned the `catalog` repository, you can install the AMQ Streams operator based on the overlay of your choice by running from the root `catalog` directory

```
oc apply -k amq-streams-operator/overlays/<channel>
```

Or, without cloning:

```
oc apply -k https://github.com/redhat-canada-gitops/catalog/amq-streams-operator/overlays/<channel>
```

As part of a different overlay in your own GitOps repo:

```
apiVersion: kustomize.config.k8s.io/v1beta1
kind: Kustomization

bases:
  - github.com/redhat-canada-gitops/catalog/amq-streams-operator/overlays/<channel>?ref=master
```