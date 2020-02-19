[![published](https://static.production.devnetcloud.com/codeexchange/assets/images/devnet-published.svg)](https://developer.cisco.com/codeexchange/github/repo/khinpyaephyosan/csr1000v_upgrade)

# CSR1000v Upgrade
This repository is a template to be used when upgrading or downgrading the Cisco IOS XE software for an existing CSR1000v. It contains sample roles and playbooks to use with either Ansible Engine or AWX Ansible Tower. It is available for use by the Cisco DevNet community through Code Exchange.

You can use this template to update the IOS XE software of one or more Cisco CSR1000v devices in one single view.

* Technology stack: This is an example of infrastructure as a code using Ansible. YAML is primary programming language(s) and code is intended to be used as Ansible roles.
* Status:  Alpha
* Tutorial: https://www.youtube.com/watch?v=64MJabLLtmg

## Instructions

There are two options to test! You can choose to use Ansible Engine or AWX Ansible Tower. 

- With Ansible Engine, [run.yml](./ansible_engine/run.yml) playbook will call roles as a single workflow to perform the upgrade.
- With AWX Ansible Tower, you need to create Job Templates and a Workflow Template. 

You also may need to update the variables in `ios_var.yaml` for your environment.

## Installation

Ansible Engine

1. Download ansible_engine folder.
2. Edit variables in [ios_var.yaml](./ansible_engine/ios_var.yaml) for your environment
3. Run [run.yml](./ansible_engine/run.yml)

AWX Ansible Tower

1. Fork the https://github.com/khinpyaephyosan/csr1000v_upgrade.git link to your Github account
2. Create a New Project with SCM TYPE is Git and Sync the project.
3. Create each Job Template for [pre_check_actions.yml](./ansible_awx/pre_check_actions.yml), [ftp_actions.yml](./ansible_awx/ftp_actions.yml), [upgrade_actions.yml](./ansible_awx/upgrade_actions.yml) and [post_check_actions.yml](./ansible_awx/post_check_actions.yml).
4. Create and run Workflow Template, which is sequentially composed by connecting [pre_check_actions.yml](./ansible_awx/pre_check_actions.yml), [ftp_actions.yml](./ansible_awx/ftp_actions.yml), [upgrade_actions.yml](./ansible_awx/upgrade_actions.yml) and [post_check_actions.yml](./ansible_awx/post_check_actions.yml) Job Templates.

## Configuration
 
 You can edit `inventory.ini` file, `ios_var.yaml`(variable file), playbooks and roles to change the workflow procedure. These are my references.
 
 * https://docs.ansible.com/ansible/latest/user_guide/playbooks.html
 * https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html
 
## Usage

Ansible Engine: $ansible-playbook run.yml -i inventory -vv

Ansible AWX Tower: Please reference this link https://www.youtube.com/watch?v=64MJabLLtmg.

## How to test the software

Ansible Engine: $ansible-playbook run.yml -i inventory --check -vv

Ansible AWS Tower: Please reference this link https://www.youtube.com/watch?v=64MJabLLtmg.


## Getting help

If you have questions, concerns, bug reports, etc., please file an issue in this repository's Issues list.

## Credits and references

1. projects that I admire: https://developer.cisco.com/iot/
2. related project: https://www.youtube.com/watch?v=E7H2_Q-gmC4
3. other sources that have meaningful impact or influence on this code: https://developer.cisco.com/, https://www.ansible.com/

