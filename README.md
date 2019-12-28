# devops-pipeline-starter

This project provisions a real life infrastructure using [devops-pipeline](https://github.com/samsquire/devops-pipeline). This project uses [platform-up](https://github.com/samsquire/platform-up) to test ansible playbooks.

![Pipeline](architecture.png)

# Contents

* Debian package repository server
* 2 CI build machines
* Prometheus instance for monitoring, monitoring via DNS
* Node exporter installed on base AMI
* Hashicorp Vault with Self signed Certificate authority for TLS
* bastion
* Kubernetes clustering


# Notes

 * SSH keys are generated on each worker and provisioned onto every other node by ansible/playbooks/worker-keys
 * Kubernetes is installed on the cluster of bastion, web, prometheus, vault servers
 * Instances have a volume service which mount volumes using the instance tags -- rather than using Terraform.

# Expanded lifecycle pipeline

Look carefully and you'll see the expanded pipeline below:
![ExpandedPipeline](architecture.expanded.png)
It's so large you have to look carefully.
