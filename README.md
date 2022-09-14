# Ubuntu / Debian Security Baseline

## Introduction

This Ansible role applies a security baseline to Debian and Ubuntu systems. The
baseline consists of controls from:

* CIS Ubuntu 20.04 Benchmark
* CIS Debian 10 Benchmark
* Kernel Self Protection Project Recommendations
* General recommendations, such as enabling UFW and automatic security updates

This baseline does not implement all recommendations. For example, it does not
implement AIDE or remote syslog. The authors use alternative tools to achieve 
those objectives. For example, Wazuh or OSSEC can be used to peform integrity 
checks, and centralized logging.

## Configuration

The role requires some site specific configuration. Such as defining your site's
logon banner, and SSH groups.

* logon_banner: Defines the banner to be displayed during local and network logons.
* ssh_allow_groups: A comma separated list of groups allowed to login via SSH.
* ssh_root_host: Host (IP or subnet) permitted to login as root using an SSH key.

## Post Role Reboot

After applying this baseline, the system must be rebooted. Several of the settings
that are applied, only take effect after reboot.

## References

This baseline was built using recommendations from the following sources:

* https://www.cisecurity.org/benchmark/ubuntu_linux/
* https://www.cisecurity.org/benchmark/debian_linux/
* https://kernsec.org/wiki/index.php/Kernel_Self_Protection_Project/Recommended_Settings
* https://help.ubuntu.com/community/Security
