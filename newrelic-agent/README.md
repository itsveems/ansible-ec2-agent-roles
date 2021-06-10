# newrelic-agent Ansible role

## Description

This role installs and configures the New Relic Infrastructure agent on Windows and Linux OS.

## Usage

Include the role in the main playbook. Customize the required variables if you want to override the ones set in default.

### Installing the Infrastructure agent

```yaml
---
- hosts: all
  roles:
    - name: newrelic-agent
      vars:
        nrinfra_agent_config:
          license_key: LICENSE_KEY
          log_file: logfile_location
```

#### Variables

##### `nrinfra_agent_state` (OPTIONAL)

Describes what you want to do with the agent:

* `'latest'` - [default] install the latest version of the agent. Also `present`.
* `'absent'` - Uninstall the agent.

##### `nrinfra_agent_version` (OPTIONAL)

What version of the agent do you want to install:

* `'*'` - [default] install the latest version of the agent.
* `'X.Y.ZZZ'` - string of the specific version number you want to install, e.g. 1.0.280

##### `nrinfra_agent_os_name` (OPTIONAL)

Specifies the target OS that the Infrastructure agent will be installed on.
Defaults to `ansible_os_family`. See list in the `meta/main.yml` file for latest list that is supported.

##### `nrinfra_agent_os_version` (OPTIONAL)

Specifies the OS version of the installer package needed for this machine.
Defaults to `ansible_lsb.major_release`. Mostly used for `RedHat` family OSs. See list in the `meta/main.yml` file for latest list.

##### `nrinfra_agent_os_codename` (OPTIONAL)

Specifies the OS codename of the installer package needed for this machine.
Defaults to `ansible_lsb.codename`. Mostly used for `Debian` family OSs. See list in the `meta/main.yml` file for latest list.

##### `nrinfra_agent_config` (REQUIRED)

Used to populate agent configuration. At a minimum you must provide `license_key`.
See the NewRelic documentation for current configuration options:
[https://docs.newrelic.com/docs/infrastructure/new-relic-infrastructure/configuration/configure-infrastructure-agent](https://docs.newrelic.com/docs/infrastructure/new-relic-infrastructure/configuration/configure-infrastructure-agent)


## Limitations

### Platforms

* RHEL
  * CentOS 7
  * CentOS 6
* Ubuntu
  * 16 Xenial
  * 14 Trusty
  * 12 Precise
* Debian
  * 10 Buster
  * 9 Stretch
  * 8 Jessie
  * 7 Wheezy

License
-------

BSD
