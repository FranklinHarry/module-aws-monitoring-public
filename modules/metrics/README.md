**Note**: This public repo contains the documentation for the private GitHub repo <https://github.com/gruntwork-io/module-aws-monitoring>.
We publish the documentation publicly so it turns up in online searches, but to see the source code, you must be a Gruntwork customer.
If you're already a Gruntwork customer, the original source for this file is at: <https://github.com/gruntwork-io/module-aws-monitoring/blob/master/modules/metrics/README.md>.
If you're not a customer, contact us at <info@gruntwork.io> or <http://www.gruntwork.io> for info on how to get access!

# Metrics modules

This folder contains modules for working with CloudWatch metrics:

* [cloudwatch-custom-metrics-iam-policy](./cloudwatch-custom-metrics-iam-policy): A module that defines
  an IAM policy that allows reading/writing CloudWatch metrics.
* [cloudwatch-memory-disk-metrics-scripts](./cloudwatch-memory-disk-metrics-scripts): Configures the EC2
  instance in this example to report custom metrics, including memory usage and disk usage, not available by default in
  CloudWatch.

Click on each module above to see its documentation. Head over to the [examples folder](/examples) for examples.

