# AMI
This app is to build AMI images for Amazon EC2 instances using AWS CLI and Hashicorp Packer

## Tools used
* [Hashicorp Packer](https://www.packer.io/)

## Prerequisites
Install [AWS CLI](https://docs.aws.amazon.com/cli/latest/userguide/install-cliv2.html) and [configure CLI profile](https://docs.aws.amazon.com/cli/latest/userguide/cli-chap-configure.html)

## Installation
### Ubuntu/Debian
Add the HashiCorp GPG key.

    curl -fsSL https://apt.releases.hashicorp.com/gpg | sudo apt-key add -

Add the official HashiCorp Linux repository.

    sudo apt-add-repository "deb [arch=amd64] https://apt.releases.hashicorp.com $(lsb_release -cs) main"

Update and install.

    sudo apt-get update && sudo apt-get install packer

### Other Operating System
To learn how to install Packer for other OS, click [here](https://learn.hashicorp.com/tutorials/packer/getting-started-install)

## Build AMI Images
### Validate template
Validate packer templates using this command:

    packer validate template_name.json

### Build template
Build packer templates using this command:

    packer build \
        -var 'aws_access_key=foo' \
        -var 'aws_secret_key=bar' \
        -var 'aws_region=us-east-1' \
        template_name.json

demo