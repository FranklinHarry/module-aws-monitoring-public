**Note**: This public repo contains the documentation for the private GitHub repo <https://github.com/gruntwork-io/module-aws-monitoring>.
We publish the documentation publicly so it turns up in online searches, but to see the source code, you must be a Gruntwork customer.
If you're already a Gruntwork customer, the original source for this file is at: <https://github.com/gruntwork-io/module-aws-monitoring/blob/master/modules/logs/elb-access-logs/README.md>.
If you're not a customer, contact us at <info@gruntwork.io> or <http://www.gruntwork.io> for info on how to get access!

# ELB Access Logs Module

This module creates an [S3 bucket](https://aws.amazon.com/s3/) that can be used to store the [access
logs](http://docs.aws.amazon.com/ElasticLoadBalancing/latest/DeveloperGuide/access-log-collection.html) for an
[Elastic Load Balancer (ELB)](https://aws.amazon.com/elasticloadbalancing/). These logs capture detailed information
about all requests sent to your load balancer. Each log contains information such as the time the request was received,
the client's IP address, latencies, request paths, and server responses. You can use these access logs to analyze
traffic patterns and to troubleshoot issues.

## Example

See the [elb-access-logs example](/examples/elb-access-logs) for an example of how to use this module.

## How do you use this module?

First, add a `module` resource to your Terraform templates that points to this elb-access-logs module:

```hcl
module "elb_access_logs_bucket" {
  source = "git::git@github.com:gruntwork-io/module-aws-monitoring.git//modules/logs/elb-access-logs?ref=v0.0.28"

  aws_region = "us-east-1"
  bucket_name = "a-unique-name-for-my-access-logs-s3-bucket"
  app_name = "my-app"
  aws_account_id = "1234567"
}
```

Note that, like all S3 buckets, the `bucket_name` must be globally unique. Next, just add an `access_logs` block
to your `aws_elb` definition:

```hcl
resource "aws_elb" "load_balancer_stg" {
  name = "my-elb"

  access_logs {
    bucket = "${module.elb_access_logs_bucket.s3_bucket_id}"
    interval = 5
    bucket_prefix = "my-app"
  }
}
```

That's it! Apply these templates and in a few minutes, you should start seeing access logs in that S3 bucket.

## How do I see the access logs?

Login to the [S3 Console](https://console.aws.amazon.com/s3/home) and you'll find the access logs in a bucket with the
name you passed in for the `bucket_name` attribute.