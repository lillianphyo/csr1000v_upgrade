# csr1000v_upgrade
This repository is a template to be used when upgrading or downgrading cisco CSR1000v ios containing sample roles and playbooks to use with either Ansible Engine or AWX Ansible Tower, and to be made available for use by the Cisco DevNet community through Code Exchange.

## Instructions

There are two options to test! You can choose with Ansible Engine or AWX Ansible Tower. With Ansible Engines, run.yml playbook will call roles as a single workflow to upgrade IOS.
With AWX Ansible Tower, need to create Job Templates and a Workflow Template. Commnly need to update variables in ios_var.yml for your invenronment needs.

----

# csr1000v_upgrade

To update IOS software one or more CISCO CSR1000v devices in one single view.


Pro tips: 

* Saving Time while updating multiple ios devices.

Other things you might include:

* Technology stack: This is nautre of infrastructure as a code using ansible , YAML is primary programming language(s) and codes are intended as ansible roles..
* Status:  Alpha
* Tutorial: https://www.youtube.com/watch?v=64MJabLLtmg


## Installation

For Ansible Engine, download ansible_engine folder and execute run.yml.
For Ansible AWX Tower, download ansible_awx folder to project directory or fork https://github.com/khinpyaephyosan/csr1000v_upgrade.git this url and run by creating a workflow tmplate.

Ansible Engine

1. Download ansible_engine folder.
2. Edit variables in ios_var.yml for your environment
3. Run run.yml

AWX Ansible Tower

1. Fork the https://github.com/khinpyaephyosan/csr1000v_upgrade.git link to your Github account
2. Create a New Project with SCM TYPE is Git and Sync the project.
3. Create each Job Template for pre_check_actions.yml, ftp_actions.yml, upgrade_actions.yml and post_check_actions.yml.
4. Create and run Workflow Template which sequentially composed by connecting pre_check_actions.yml, ftp_actions.yml, upgrade_actions.yml and post_check_actions.yml Job Templates.

## Configuration
 
 You can edit all inventory file,ios_var.yml(variable file), playbooks and roles to change the workflow procedure. This is my references.
 https://docs.ansible.com/ansible/latest/user_guide/playbooks.html
 https://docs.ansible.com/ansible/latest/user_guide/playbooks_reuse_roles.html
 
## Usage

Ansible Engine
$ansible-playbook run.yml -i inventory -vv

Ansible AWX Tower
Please reference this link (https://www.youtube.com/watch?v=64MJabLLtmg).

## How to test the software

Ansible Engine
$ansible-playbook run.yml -i inventory --check -vv

Ansible AWS Tower
Please reference this link (https://www.youtube.com/watch?v=64MJabLLtmg).

## Known issues

Document any known significant shortcomings with the code. If using the [Issue Tracker](./issues), make that known here and provide any templates or conventions to be followed when opening a new issue. 

## Getting help

If you have questions, concerns, bug reports, etc., please file an issue in this repository's [Issue Tracker](./issues).

## Getting involved

Because one or more CSR1000v devices are need to update in my environment. I just want to help this operation process faster.

----

## Licensing info

A license is required for others to be able to use your code. An open source license is more than just a usage license, it is license to contribute and collaborate on code. Open sourcing code and contributing it to [Code Exchange](https://developer.cisco.com/codeexchange/)  requires a commitment to maintain the code and help the community use and contribute to the code. 

Choosing a license can be difficult and depend on your goals for your code, other licensed code on which your code depends, your business objectives, etc.   This template does not intend to provide legal advise. You should seek legal counsel for that. However, in general, less restrictive licenses make your code easier for others to use.

> Cisco employees can find licensing options and guidance [here](https://wwwin-github.cisco.com/eckelcu/DevNet-Code-Exchange/blob/master/GitHubUsage.md#licensing-guidance).

Once you have determined which license is appropriate, GitHub provides functionality that makes it easy to add a LICENSE file to a GitHub repo, either when creating a new repo or by adding to an existing repo.

When creating a repo through the GitHub UI, you can click on *Add a license* and select from a set of [common open source licenses](https://opensource.org/licenses). See [detailed instructions](https://help.github.com/articles/licensing-a-repository/#applying-a-license-to-a-repository-with-an-existing-license).

Once a repo has been created, you can easily add a LICENSE file through the GitHub UI at any time. Simply select *Create New File*, type *LICENSE* into the filename box, and you will be given the option to select from a set of common open source licenses. See [detailed instructions](https://help.github.com/articles/adding-a-license-to-a-repository/).

Once you have created the LICENSE file, be sure to update/replace any templated fields with appropriate information, including the Copyright. For example, the [3-Clause BSD license template](https://opensource.org/licenses/BSD-3-Clause) has the following copyright notice:

`Copyright (c) <2019>, <Cisco Systems>`

See the [LICENSE](./LICENSE) for this template repo as an example.

Once your LICENSE file exists, you can delete this section of the README, or replace the instructions in this section with a statement of which license you selected and a link to your license file, e.g.

This code is licensed under the BSD 3-Clause License. See [LICENSE](./LICENSE) for details.

Some licenses, such as Apache 2.0 and GPL v3, do not include a copyright notice in the [LICENSE](./LICENSE) itself. In such cases, a NOTICE file is a common place to include a copyright notice. For a very simple example, see [NOTICE](./NOTICE). 

In the event you make use of 3rd party code, it is required by some licenses, and a good practice in all cases, to provide attribution for all such 3rd party code in your NOTICE file. For a great example, see [https://github.com/cisco/ChezScheme/blob/master/NOTICE]().   

----

## Credits and references

1. projects that I admire: https://developer.cisco.com/iot/
2. related project: https://www.youtube.com/watch?v=E7H2_Q-gmC4
3. other sources that have meaningful impact or influence on this code: https://developer.cisco.com/, https://www.ansible.com/
