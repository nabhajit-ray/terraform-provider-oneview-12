# terraform-provider-oneview

[![Build Status](https://travis-ci.org/HewlettPackard/terraform-provider-oneview.svg?branch=master)](https://travis-ci.org/HewlettPackard/terraform-provider-oneview)

A Terraform provider for oneview

## Installing `terraform-provider-oneview` with Go

* Install Go 1.11. For previous versions, you may have to set your `$GOPATH` manually, if you haven't done it yet.
* Install Terraform 0.12.x [from here](https://www.terraform.io/downloads.html) and save it into `/usr/local/bin/terraform` folder (create it if it doesn't exists). This provider DOES NOT SUPPORT Terraform 0.12 or above.
* Download the code by issuing a `go get` command.

```bash
# Download the source code for terraform-provider-oneview
# and build the needed binary, by saving it inside $GOPATH/bin
$ go get -u github.com/HewlettPackard/terraform-provider-oneview

# Copy the binary to have it along the terraform binary
$ mv $GOPATH/bin/terraform-provider-oneview /usr/local/bin/terraform
```



## Using `terraform-provider-oneview` with Docker


We also provide a lightweight and easy way to test and execute `terraform-provider-oneview`. The `hewlettpackardenterprise/hpe-oneview-sdk-for-terraform:<tag>` docker image contains an installation of Terraform and our provider you can use by just pulling down the Docker Image:
Docker Store image tag consist of two sections: <sdk_version-OV_version>

```bash
# Download and store a local copy of terraform-provider-oneview and
# use it as a Docker image.
$ docker pull hewlettpackardenterprise/hpe-oneview-sdk-for-terraform:v1.5.0-OV5.4

# Run docker commands using the "ash" shell from Alpine, this will in turn create
# a sh session where you can create files, issue commands and execute both
# terraform and the provider with ease.
$ docker run -it hewlettpackardenterprise/hpe-oneview-sdk-for-terraform:v1.5.0-OV5.4 /bin/sh
```

### Provider Information

For authentication, you need to provide the provider information in examples:


```bash
provider "oneview" {
	ov_username = "<ov_username>"
	ov_password = "<ov_password>"
	ov_endpoint = "<ov_endpoint>"
	ov_sslverify = true/false
	ov_apiversion = <ov_apiversion>
	ov_domain = "<ov_domain>"
	ov_ifmatch = "*"
}
```

Note: Currently this SDK supports OneView API 2000 minimally where we can test OneView API 2000 version with this SDK. No new fields have been added/deleted to support API2000 version. Complete support will be done in next releases.If  API version is not provided then appliance's API version will be used. If API version used is not supported then error will be thrown.

### License

This project is licensed under the Apache 2.0 license.

## Version and changes

To view history and notes for this version, view the [Changelog](CHANGELOG.md).
