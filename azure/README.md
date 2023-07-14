# Level Up - A Hands on Crossplane Workshop for Azure

## Install Azure Provider
1. [Check the Upbound marketplace](https://marketplace.upbound.io/providers/upbound/provider-azure/) for the latest version of the provider (ie-v0.26.0).
2. Update the spec.package in [the provider config](.3-other/az-provider.yaml) with the latest version.
3. `kubectl -f 3-other/az-provider.yaml`
4. `kubectl get providers` and verify INSTALLED and HEALTHY are true.

## Configure Provider
1. [Create a Kubernetes secret for Azure](https://docs.crossplane.io/latest/getting-started/provider-azure/#create-an-azure-service-principal)
    * BE SURE TO CREATE THE SECRET IN THE upbound-system NAMESPACE and not crossplane-system.
2. Install the provider config `kubectl apply -f 3-other/az-provider-cfg.yaml`
3. `kubectl get providerconfigs` and verify the default provider is created

## Excercises

Go in to each folder below to follow the README for each section.

* [Managed Resources](1-managed-resources)
* [Composite Resource Definition](2-xrd)

Each folder will create one the following:
* Resource Group
* Storage Account
* Storage Container

## Notes
Each folder can be run and there should be no naming conflicts.
