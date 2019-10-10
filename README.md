# tf_kube_aws_creds_provider_via_vault

This module allows a Kubernetes service account to retrieve AWS credentials for an IAM role by creating the following vault
resources:

- An AWS secret role that assumes a particular IAM role
- A Kubernetes auth role with permissions to use that AWS secret role

## Usage

```hcl
module "tf_kube_aws_creds_provider_via_vault" {
  source = "github.com/utilitywarehouse/tf_kube_aws_creds_provider_via_vault"

  kube_namespace = "example-namespace"
  kube_sa_name   = "example"
  aws_role_arn   = "arn:aws:iam::000000000000:role/example"
}
```

Check `variables.tf` for detailed descriptions and optional variables.
