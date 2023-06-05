# Terraform Kind cluster and Flux Bootstrap

This project uses Terraform to create a Kubernetes cluster on local Kind cluster, set up a Github repository to store Kubernetes manifests, and bootstrap the cluster using Flux.

## Pre-requisites

- Terraform installed (version >= 1.0.3)
- Github account

## Configuration

Update the values in `vars.auto.tfvars` file to match your configuration.

## Terraform modules used

### `hashicorp-tls-keys`

This module creates a TLS private key and self-signed certificate. It exports the private key in PEM format and the public key in OpenSSH format.

### `kind_cluster`

This module creates a local Kind clusters (Kubernetes clusters using Docker).

### `github-repository`

This module creates a private Github repository and a deploy key. The public key is passed from the `hashicorp-tls-keys` module.

### `fluxcd-flux-bootstrap`

This module installs Flux in the Kubernetes cluster and sets it up to read manifests from the Github repository created by the `github-repository` module. It also generates a private key for Flux to use to authenticate with Github.

## Usage

```shell
terraform init
terraform apply
```
## License
MIT License. See LICENSE for full details.
