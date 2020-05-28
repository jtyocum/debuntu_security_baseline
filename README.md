# Ubuntu / Debian Security Baseline

## Introduction

This Ansible role applies a security baseline to Debian and Ubuntu systems. The
baseline consists of controls from:

* CIS Ubuntu 16.04 Benchmark
* CIS Debian 8 Benchmark
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

## Post Role Reboot

After applying this baseline, the system must be rebooted. Several of the settings
that are applied, only take effect after reboot.
