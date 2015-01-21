# Dynatrace-Collector-Ansible

An [Ansible](ansible.com) role for automated deployments of the [Dynatrace](bit.ly/dttrial) Collector. 

**Note**: Currently, we support only Linux hosts, support for installing Windows hosts is in the making.

## Download

The role is available via:

- [Ansible Galaxy](https://galaxy.ansible.com/list#/roles/)
- [GitHub](https://github.com/Dynatrace/Dynatrace-Collector-Ansible)

## Requirements

Download the Dynatrace Collector installer from [downloads.compuwareapm.com](downloads.compuwareapm.com) and place the artifact as ```dynatrace-collector.jar``` in the role's ```files``` directory from where it will be picked up during the automated installation.

## Role Variables

As defined in ```defaults/main.yml```:

| Name                                            | Default                 | Description |
|-------------------------------------------------|-------------------------|-------------|
| *dynatrace_collector_installer_bitsize*         | 64                      | 32 or 64    |
| *dynatrace_collector_linux_install_dir*         | /opt                    | The Dynatrace Collector will be installed into the directory *$dynatrace_collector_linux_install_dir*/dynatrace-*$major*-*$minor*-*$rev*, where *$major*, *$minor* and *$rev* are given by the installer. A symbolic link to the actual installation directory will be created in *$dynatrace_collector_linux_install_dir*/dynatrace. |
| *dynatrace_collector_linux_installer_file_name* | dynatrace-collector.jar | The file name of the Dynatrace Collector installer in the role's ```files``` directory. |
| *dynatrace_collector_role_name*                 | Dynatrace-Collector     | The actual name of this role in an [Ansible Playbook's](http://docs.ansible.com/playbooks.html) ```roles``` directory. |

## Example Playbook

	- hosts: all
	  roles:
	    - { role: Dynatrace-Collector }

## Additional Resources

- [Slide Deck: Automated Deployments](slideshare.net/MartinEtmajer/automated-deployments-slide-share)
- [Slide Deck: Introduction to Automated Deployments with Ansible](http://www.slideshare.net/MartinEtmajer/introduction-to-automated-deployments-with-ansible)

## Questions?

Feel free to post your questions on the Dynatrace Community's [Continuous Delivery Forum](https://community.dynatrace.com/community/pages/viewpage.action?pageId=46628921).

## License

Licensed under the MIT License. See the LICENSE file for details.
