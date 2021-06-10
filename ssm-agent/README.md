# SSM-Agent Role

The ssm-agent role includes the tasks to configure agent present on the targeted TRULOGIS Windows hosts. For Linux target hosts, the agent is first installed and then configured.

## Requirements

All the tasks in the ssm-agent role require a target Windows or Linux machine/instance.

## Role Details

The tasks for Windows SSM agent configuration include configuring the agent and Windows Update to use proxy and run three documents listed below using "aws ssm send-command" AWS cli command from the Ansible control machine.

* AWS-UpdateSSMAgent

* AWS-ConfigureWindowsUpdate

* AWS-RunPatchBaseline (Operation Scan and Install)

The tasks for Linux SSM agent involve its installation and configuration to use proxy for inbound and outbound communication to AWS SSM and running two documents (AWS-UpdateSSMAgent and AWS-RunPatchBaseline - Scan and Install Operation) out of the three mentioned above.


## Usage
Below are sample usages for the role in a playbook. Please only use the vars to override the existing defaults which have already been set.

##### For deploying ssm agent configuration to a Windows or Linux target machine by overriding proxy variables.
```yaml
- hosts: all
  roles:
    - role: ssm-agent
      proxy: internal-proxy.example.internal:8080
      proxy_override: "169.254.169.254;localhost;<local>"
```

## License

    Apache-2.0

## Author Information

    itsveems