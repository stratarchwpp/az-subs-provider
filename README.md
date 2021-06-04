# Terraform Provider for Azure Preview

this is an exact copy of the inovationnorway code. None of the code has been changed. we mearly just need to ensure   
that this provider doesn't get removed and so have created this duplicate provider   

![](https://github.com/innovationnorway/terraform-provider-azure-preview/workflows/test/badge.svg)

## Requirements

-	[Terraform](https://www.terraform.io/downloads.html) >= 0.12
-	[Go](https://golang.org/doc/install) >= 1.14

## Usage

```hcl
provider "azure-preview" {}

resource "azurepreview_subscription" "example" {
  name               = "example"
  enrollment_account = "6d38255d-8321-4f17-8ddd-3bd94c57d988"
  offer_type         = "MS-AZR-0148P"
  provider           = azure-preview
}
```

## Contributing

To build the provider:

```sh
$ go build
```

To test the provider:

```sh
$ go test -v ./...
```

To run all acceptance tests:

*Note:* Acceptance tests create real resources, and often cost money to run.

```sh
$ TF_ACC=1 go test -v ./...
```

To run a subset of acceptance tests:

```sh
$ TF_ACC=1 go test -v ./... -run=TestAccAzurePreviewSubscription
```
