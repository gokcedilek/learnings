### Managing AWS Users

- Each entry in the AWS CLI credentials file is a [named profile](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-profiles.html).
- To create & use a new profile:
  - Create the user from the AWS Management console: `IAM` &#8594; `users` called `terraform-demo-1`
  - Get the access key ID & secret access key
  - From the CLI, run [`aws configure --profile terraform-demo-1`](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-quickstart.html) and provide the access credentials
  - This will add the new profile to the credentials file (`cat ~/.aws/credentials`)
  - By default, `aws iam get-user` will return the default profile.
  - Override the profile using [env variables](https://docs.aws.amazon.com/cli/latest/userguide/cli-configure-envvars.html): `export AWS_PROFILE=terraform-demo-1`
  - After this, `aws iam get-user` will now return the `terraform-demo-1` profile. Note: For this operation to work, the user/profile `terraform-demo-1` needs to have the `IAMReadOnlyAccess` policy attached (from the management console).
