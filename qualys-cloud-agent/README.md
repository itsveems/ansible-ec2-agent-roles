# Qualys-Cloud-Agent Role

The qualys-cloud-agent role includes the tasks to install and activate Qualys Cloud agent on all the TRULOGIS Windows and Linux targets.

## Requirements

All the tasks in the qualys-cloud-agent role need a target Windows or Redhat Linux machine/instance.

The tasks for Windows Qualys agent installation include downloading the agent from TRULOGIS Interim IT repository hosted in S3 bucket and running the installation and activation of the agent on the target host with separate activation IDs for the three TRULOGIS lifecycles (live, prelive and test).

## Usage
Below are sample usages for the role in a playbook. Please only use the vars to override the existing defaults which have already been set. Current implementation downloads the agent binary artifacts from TRULOGIS Interim IT repository hosted in S3 bucket.

##### For deploying qualys agent configuration to a Windows target machine.
```yaml
- hosts: all
  roles:
    - role: qualys-cloud-agent
      customer_id: "11111111-2222-3333-4444-555555555555"
      activation_id: "7777777-4444-1111-3333-999999999999"
```

## License

    Apache-2.0