# Terraform Beginner Bootcamp 2023

## Install the Terraform CLI
[Install Terraform CLI](https://developer.hashicorp.com/terraform/tutorials/aws-get-started/install-cli)

## Understanding and implementing Shebang
[Shebang](https://en.wikipedia.org/wiki/Shebang_(Unix))

## Understanding Unix perfmissions
[Linux permissions](https://en.wikipedia.org/wiki/Chmod)

### AWS CLI Installation

AWS CLI is installed for the project via the bash script [`./bin/install_aws_cli`]

[Getting started install aws cli](https://docs.aws.amazon.com/cli/latest/userguide/getting-started-install.html)

[AWS CLI ENV Vars](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html)

We can check if our AWS crdentials is configuerd correctly by running the folloring AWS CLI command:
```
sh
aws sts get-caller-identity
```

If it is successful you should see a JSON payload return that looks like this:

```json
{
    "UserId": "AIDA56YXAESMPZLN42HO4",
    "Account": "1234567891012,
    "Arn": "arn:aws:iam::959436563608:user/terraform-user"
}
```

We will need to generate AWS CLI credits from IAM User in order to use AWS CLI

## Terraform Basics

### Terraform Registry

Terraform sources their providers and modules from the Terraform registry which located at [registry.terraform.io](https://registry.terraform.io/)

- **Provideers** are interfaces to APIs that will allow you to create resources in terraform.

- **Modules** are a way to make large amounts of terraform code modular, portable and shareable.

## Terraform Console

We can see a list of all the Terraform commands by simply typing `terraform`

#### Terraform Init

At the start of a new terraform project we will run `terraform init` to downloadd the binaries for the terraform providers that we will use in this project

#### Terraform Plan

This will generate out a changeset, about the state of our infrastructure and what will be changed.

W can output this changeset ie. "plan" to  be passed to an apply , but often you can just ignore outputting.

#### Terraform apply

`terraform apply`

This will run a plan and pass the changeset to be executed by terraform. Apply should prompt yes or no.

If we want to automatically approve and apply we can provide the auto approve fag eg. `terraform apply --auto-approve`.

### TErraform Lock Files

`.terraform.lock.chl` contains the locked versioning for the providers or modules that should be used with this project.

The Terrraform Lock File should be committed to your VErsion Control System (VCS) eg. Github

### TErraform state files

`.terraform.tfstate` contain information about the current state ogf your infrastructure.

this file **should not be committed** to your VCS.

This file can contain sensitive data.

If you lose thise file, you lose knowing the state of your infrastructure.

`.terraform.tfstate.backup` is the  previous state file state.

### Terraform Directory

`.terraform` directory contains binaries of terraform providers.