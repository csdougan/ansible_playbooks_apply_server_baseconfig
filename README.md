
# Server Build Ansible Tower

IT server base operating system configuration for Linux. 

## Introduction
This repository contains the playbooks called by Ansible Tower in order to apply relevant build roles against new hosts.
The intention is to apply both Windows and Linux configuration- however Windows is still under development.
The playbook in this repository does the following -
- Creates an entry for the host within an Inventory in Ansible Tower
- Creates groups relating to the host in that Inventory if they don't already exist
- Adds host to the relevant groups
- Applies ansible role to configure a new vms operating system after that vm has been cloned from a template.
- Installs relevant system agents like Splunk, McAfee 
- Configures SSSD on server


## Operating Systems
This configuration supports the following operating systems:
- **RedHat Enterprise Linux 6**
- **RedHat Enterprise Linux 7**
- **CentOS 7**

## Platforms
The following platforms are supported:
- **VMware vSphere (A)**
- **VMware vSphere (B)**

## Input Variables
The following variables must be passed into the role:
- input_hostname (this is the shortname of the new vm being built - e.g. hostname-abc123000)
- input_env (e.g. dev/prd/sit/pdr etc.)
- input_envinstance (defaults to 1)
- input_appname (e.g. group_myapp)
- input_appid (e.g. abcd)
- input_platform (e.g. was_servers, oracle_db_servers)
- input_componentid (optional - e.g. myapp)
- input_location (e.g. woking)
- input_organisation (optional) (OrgA/OrgB/OrgC)

## Owners
Any updates should be submitted via a pull request for approval.
# ansible_playbooks_apply_server_baseconfig
