# Level Up - A Hands on Crossplane Workshop for GCP

## Install GCP Provider
1. [Check the Upbound marketplace](https://marketplace.upbound.io/providers/upbound/provider-gcp-storage/) for the latest version of the provider (ie-v0.26.0).
2. Update the spec.package in [the provider config](.3-other/gcp-provider.yaml) with the latest version.
3. `kubectl -f 3-other/gcp-provider.yaml`
4. `kubectl get providers` and verify INSTALLED and HEALTHY are true.

## Configure Provider
1. [Create a Kubernetes secret for Azure](https://docs.crossplane.io/latest/getting-started/provider-gcp/#create-a-kubernetes-secret-for-gcp)
   * BE SURE TO CREATE THE SECRET IN THE upbound-system NAMESPACE and not crossplane-system.
2. Modify projectID field in 3-other/gcp-project-cfg.yaml to your google project ID.
3. Install the provider config `kubectl apply -f 3-other/gcp-provider-cfg.yaml`
4. `kubectl get providerconfigs` and verify the default provider is created

## Excercises

Go in to each folder below to follow the README for each section.

* [Managed Resources](1-managed-resources)
* [Composite Resource Definition](2-xrd)

Each folder will create one the following:
* Storage Bucket
* Bucket Access Control

## Notes
Each folder can be run and there should be no naming conflicts.
