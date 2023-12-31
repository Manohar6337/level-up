# Managed Resources - AWS

This folder has each managed resource in a file to be built by itself as a single resource. Installing all of them will
create the following:

* S3 bucket
* IAM Role
* IAM Policy
* IAM RolePolicyAttachment

This is a very basic approach to using Managed resources in Crossplane. It uses only the managed resources from the
provider and not within a composition. It still provides the benefits of using the kubernetes resource model, but does not
give the simple self-service API of using compositions.

## Steps
1. Change directories to aws/1-managed-resources
2. In each file in the folder, search and replace the word **CHANGE-ME** and replace with your own identifier.
3. To test the provider setup, deploy the s3 bucket only
   * `kubectl apply -f bucket.yaml`
   * Verify: `kubectl get buckets.s3.aws.upbound.io`
4. Once the bucket is successfully deployed, apply all manifests in the folder:
   * `kubectl apply -f .`
5. Verify all managed resources: 
   * `kubectl get managed -l crossplane-demo=aws-levelup-managed-resources`
6. Cleanup, if desired
   * `kubectl delete -f .`

## Next
* [Build the same resources in a composition](../2-xrd)