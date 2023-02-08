Under development, not tested yet.

Steps to install demo:

1. Install the OpenShift GitOps manually in the cluster, it will be used to bootstrap everything else

2. Deploy the infra components:

```
kustomize build infra/argo/base --enable-helm | oc apply -f -
```

* Note this will update the openshift-gitops operator configuration and it will become self-managing

Wait for all applications to be in sync before moving to the next step

3. Install the demo application with:

```
kustomize build demo/argo/base --enable-helm | oc apply -f -
```