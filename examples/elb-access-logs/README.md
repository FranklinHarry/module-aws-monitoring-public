**Note**: This public repo contains the documentation for the private GitHub repo <https://github.com/gruntwork-io/module-aws-monitoring>.
We publish the documentation publicly so it turns up in online searches, but to see the source code, you must be a Gruntwork customer.
If you're already a Gruntwork customer, the original source for this file is at: <https://github.com/gruntwork-io/module-aws-monitoring/blob/master/examples/elb-access-logs/README.md>.
If you're not a customer, contact us at <info@gruntwork.io> or <http://www.gruntwork.io> for info on how to get access!

# ELB Access Logs Example

This is an example of how to configure an Elastic Load Balancer (ELB) so that it stores its access logs in an S3
bucket using the following modules:

* [elb-access-logs](/modules/logs/elb-access-logs): Creates an S3 bucket to store ELB access logs, along with the
  appropriate access policy and lifecycle rules.

## Quick start

To try these templates out you must have Terraform installed (minimum version: `0.6.11`):

1. Open `vars.tf`, set the environment variables specified at the top of the file, and fill in any other variables that
   don't have a default, including setting `ami` to the AMI you built in step 1.
1. Run `terraform get`.
1. Run `terraform plan`.
1. If the plan looks good, run `terraform apply`.

## How do I see the access logs for my ELB?

The `access_logs_s3_bucket_id` output variable will give you the name of the S3 bucket where your access logs are
stored. Find this bucket in the [S3 console](https://console.aws.amazon.com/s3/home), click down through the folders
until you find your ELB's name, and inside you'll find the access logs. See [Monitor Your Load Balancer Using Elastic
Load Balancing Access Logs](http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/access-log-collection.html)
for details on the log file format.