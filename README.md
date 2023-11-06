# terraform-gcp-kms
# Google Cloud Infrastructure Provisioning with Terraform
## Table of Contents

- [Introduction](#introduction)
- [Usage](#usage)
- [Module Inputs](#module-inputs)
- [Module Outputs](#module-outputs)
- [License](#license)

## Introduction
This project deploys a Google Cloud infrastructure using Terraform to create kms .
## Usage
To use this module, you should have Terraform installed and configured for GCP. This module provides the necessary Terraform configuration for creating GCP resources, and you can customize the inputs as needed. Below is an example of how to use this module:
```hcl
module "kms_key" {
  source           = "git::https://github.com/opz0/terraform-gcp-kms.git?ref=v1.0.0"
  name             = "app"
  environment      = "test"
  location         = "asia-northeast1"
  service_accounts = ["serviceAccount:xxxxxxxxxx-compute@developer.gserviceaccount.com"]
  role             = "roles/editor"
}
```
This example demonstrates how to create various GCP resources using the provided modules. Adjust the input values to suit your specific requirements.
## Module Inputs

- 'name'  :The name of the service account.
- 'environment': The environment type.
- 'project_id' : The GCP project ID.
- 'location': The location for the KeyRing.
- 'service_accounts': Identities that will be granted the privilege in role.
- 'role' : The role that should be applied.

## Module Outputs
Each module may have specific outputs. You can retrieve these outputs by referencing the module in your Terraform configuration.

- 'key_id' : An identifier for the resource with format.
- 'keyring_name': Name of the keyring.
- 'keyring': Self link of the keyring.
- 'etag': The etag of the project's IAM policy.

## Examples
For detailed examples on how to use this module, please refer to the 'examples' directory within this repository.

## Author
Your Name Replace '[License Name]' and '[Your Name]' with the appropriate license and your information. Feel free to expand this README with additional details or usage instructions as needed for your specific use case.

## License
This project is licensed under the MIT License - see the [LICENSE](https://github.com/opz0/terraform-gcp-kms/blob/readme/LICENSE) file for details.
