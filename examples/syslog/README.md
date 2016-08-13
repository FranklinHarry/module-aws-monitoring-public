**Note**: This public repo contains the documentation for the private GitHub repo <https://github.com/gruntwork-io/module-aws-monitoring>.
We publish the documentation publicly so it turns up in online searches, but to see the source code, you must be a Gruntwork customer.
If you're already a Gruntwork customer, the original source for this file is at: <https://github.com/gruntwork-io/module-aws-monitoring/blob/master/examples/syslog/README.md>.
If you're not a customer, contact us at <info@gruntwork.io> or <http://www.gruntwork.io> for info on how to get access!

# Syslog Module Example

This is an example of how to use the [configure-syslog module](/modules/logs/configure-syslog) to configure rate
limiting and log rotation for syslog. The example contains a [Packer](https://www.packer.io/) template that creates
Ubuntu and Amazon Linux AMIs with syslog configured using the `configure-syslog` module.

## Quick start

To build the AMIs:

1. Install [Packer](https://www.packer.io/)
1. Set your [GitHub access token](https://help.github.com/articles/creating-an-access-token-for-command-line-use/) as
   the environment variable `GITHUB_OAUTH_TOKEN`.
1. Run `packer build syslog-example-amazon-linux-ubuntu.json`