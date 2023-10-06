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