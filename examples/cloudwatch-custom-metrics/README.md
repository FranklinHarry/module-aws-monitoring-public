**Note**: This public repo contains the documentation for the private GitHub repo <https://github.com/gruntwork-io/module-aws-monitoring>.
We publish the documentation publicly so it turns up in online searches, but to see the source code, you must be a Gruntwork customer.
If you're already a Gruntwork customer, the original source for this file is at: <https://github.com/gruntwork-io/module-aws-monitoring/blob/master/examples/cloudwatch-custom-metrics/README.md>.
If you're not a customer, contact us at <info@gruntwork.io> or <http://www.gruntwork.io> for info on how to get access!

# CloudWatch Custom Metrics Example

This is an example of how to set report custom metrics from an EC2 instance using the following modules:

* [cloudwatch-custom-metrics-iam-policy](/modules/metrics/cloudwatch-custom-metrics-iam-policy): A module that defines
  an IAM policy that allows reading/writing CloudWatch metrics.
* [cloudwatch-memory-disk-metrics-scripts](/modules/metrics/cloudwatch-memory-disk-metrics-scripts): Configures the EC2
  instance in this example to report custom metrics, including memory usage and disk usage, not available by default in
  CloudWatch.

## Quick start

To try these templates out you must have Terraform installed (minimum version: `0.6.11`):

1. Build an AMI using the [Packer](https://www.packer.io/) template under `packer/build.json`.
1. Open `vars.tf`, set the environment variables specified at the top of the file, and fill in any other variables that
   don't have a default, including setting `ami` to the AMI you built in step 1.
1. Run `terraform get`.
1. Run `terraform plan`.
1. If the plan looks good, run `terraform apply`.

## How do I get notifications from these alarms?

To see the memory and disk usage metrics, login to the [CloudWatch Metrics
Dashboard](https://console.aws.amazon.com/cloudwatch/home#metrics:) and look for the "Linux System Metrics". You should
see:

* DiskSpaceUtilization
* MemoryUtilization
