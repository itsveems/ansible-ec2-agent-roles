# ansible-ec2-agent-roles

Ansible roles that install and configure monitoring and security agents on
Trulogis EC2 hosts. They are applied by the `provisioning/` playbook in
[ansible-playbooks](https://github.com/itsveems/ansible-playbooks).

## Roles

| Role | What it does |
|------|--------------|
| [`ssm-agent`](ssm-agent/) | Configures the AWS Systems Manager agent on Windows and Linux targets, including proxy settings for hosts without direct internet egress. |
| [`qualys-cloud-agent`](qualys-cloud-agent/) | Installs and activates the Qualys Cloud Agent, using a separate activation ID per lifecycle (development, live, prelive, research and test). |
| [`newrelic-agent`](newrelic-agent/) | Installs the New Relic Infrastructure agent and writes its licence key. |

## Variables

Activation IDs and licence keys are read from the `vars/vaulted-*.yml` files.
The copies in this repository hold placeholder values.

## Status

Reference snapshot, unmaintained. Written in 2021.
