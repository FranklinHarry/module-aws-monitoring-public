**Note**: This public repo contains the documentation for the private GitHub repo <https://github.com/gruntwork-io/module-aws-monitoring>.
We publish the documentation publicly so it turns up in online searches, but to see the source code, you must be a Gruntwork customer.
If you're already a Gruntwork customer, the original source for this file is at: <https://github.com/gruntwork-io/module-aws-monitoring/blob/master/modules/logs/README.md>.
If you're not a customer, contact us at <info@gruntwork.io> or <http://www.gruntwork.io> for info on how to get access!

# Log modules

This folder contains modules that help with logging:

* [cloudwatch-log-aggregation-iam-policy](./cloudwatch-log-aggregation-iam-policy): A module that defines
  an IAM policy that allows reading/writing CloudWatch log data.
* [cloudwatch-log-aggregation-scripts](./cloudwatch-log-aggregation-scripts): Scripts to install and
  configure the CloudWatch Logs Agent.
* [elb-access-logs](./elb-access-logs): Creates an S3 bucket to store ELB access logs, along with the
  appropriate access policy and lifecycle rules.

Click on each module above to see its documentation. Head over to the [examples folder](/examples) for examples.

