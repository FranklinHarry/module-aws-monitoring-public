**Note**: This public repo contains the documentation for the private GitHub repo <https://github.com/gruntwork-io/module-aws-monitoring>.
We publish the documentation publicly so it turns up in online searches, but to see the source code, you must be a Gruntwork customer.
If you're already a Gruntwork customer, the original source for this file is at: <https://github.com/gruntwork-io/module-aws-monitoring/blob/master/modules/alarms/ecs-service-with-alb-alarms/README.md>.
If you're not a customer, contact us at <info@gruntwork.io> or <http://www.gruntwork.io> for info on how to get access!

# ECS Service with ALB Alarms

To add CloudWatch alarms for use with the Gruntwork Module [ecs-service-with-alb](
https://github.com/gruntwork-io/module-ecs/tree/master/modules/ecs-service-with-alb), use the [alb-target-group-alarms](
../alb-target-group-alarms) module. This is because all of an ECS Service's containers exist within an [ALB Target Group](
http://docs.aws.amazon.com/elasticloadbalancing/latest/application/load-balancer-target-groups.html).