# Timezone Role for Ansible

[![Build Status](https://travis-ci.org/petemcw/ansible-role-timezone.svg?branch=master)](https://travis-ci.org/petemcw/ansible-role-timezone)

This role manages the timezone.

## Role Variables

The variables that can be passed to this role and a brief description about
them are as follows:

```yaml
# Enable/Disable timezone tasks
timezone_enabled: true

# Default timezone
timezone: Etc/UTC

# Timezone dependent services list 
timezone_dependent_services: []
```

## Examples

1. Configure the timezone with the defaults:

    ```yaml
    ---
    # This playbook configures timezone

    - name: Configure timezone on all nodes
      hosts: all
      roles:
        - timezone
    ```

2. Configure a non-default timezone and services that need to pick up new timezone:

    ```yaml
    ---
    # This playbook configures timezone

    - name: Configure timezone on all nodes
      hosts: all
      roles:
        - timezone
      vars:
        timezone: America/Chicago
        timezone_dependent_services: [rsyslog, sendmail]
    ```

## Dependencies

None.

## License

MIT
