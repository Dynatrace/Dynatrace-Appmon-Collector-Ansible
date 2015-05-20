# Dynatrace-Collector-Ansible

An [Ansible](http://www.ansible.com) role for automated deployments of the [Dynatrace](http://bit.ly/dttrial) Collector. 

## Download

The role is available via:

- [Ansible Galaxy](https://galaxy.ansible.com/list#/roles/2621)
- [GitHub](https://github.com/Dynatrace/Dynatrace-Collector-Ansible)

## Requirements

Download the Dynatrace Collector installer from [downloads.dynatrace.com](downloads.dynatrace.com) and place the artifact as ```dynatrace-collector.jar``` in the role's ```files/linux``` directory from where it will be picked up during the automated installation. Alternatively, you can make the Dynatrace Collector installer available at an HTTP, HTTPS or FTP resource and point the installation script to the right location, see below.

## Role Variables

As defined in ```defaults/main.yml```:

| Name                                            | Default                                         | Description |
|-------------------------------------------------|-------------------------------------------------|-------------|
| *dynatrace_collector_installer_bitsize*         | 64                                              | 32 or 64    |
| *dynatrace_collector_linux_install_dir*         | /opt                                            | The Dynatrace Collector will be installed into the directory *$dynatrace_collector_linux_install_dir*/dynatrace-*$major*-*$minor*-*$rev*, where *$major*, *$minor* and *$rev* are given by the installer. A symbolic link to the actual installation directory will be created in *$dynatrace_collector_linux_install_dir*/dynatrace. |
| *dynatrace_collector_linux_installer_file_name* | dynatrace-collector.jar                         | The file name of the Dynatrace Collector installer in the role's ```files``` directory. |
| *dynatrace_collector_linux_installer_file_url*  | http://localhost/dynatrace/dynatrace-agents.jar | A HTTP, HTTPS or FTP URL to the Dynatrace Collector installer in the form (http\|https\|ftp)://[user[:pass]]@host.domain[:port]/path. |
| *dynatrace_collector_agent_port*                | 9998                                            | The port where the Collector shall listen for agent connections. |
| *dynatrace_collector_server_hostname*           | localhost                                       | The location of the Server the Collector shall connect to. |
| *dynatrace_collector_server_port*               | 6698                                            | The port on the Server the Collector shall connect to. Use either ```6698``` (non-SSL) or ```6699``` (SSL). |
| *dynatrace_collector_role_name*                 | dynatrace.Dynatrace-Collector                   | The actual name of this role in an [Ansible Playbook's](http://docs.ansible.com/playbooks.html) ```roles``` directory. |

## Example Playbook

	- hosts: all
	  roles:
	    - role: dynatrace.Dynatrace-Collector

## Additional Resources

- [Blog: How to Automate Enterprise Application Monitoring with Ansible](http://apmblog.dynatrace.com/2015/03/04/how-to-automate-enterprise-application-monitoring-with-ansible/)
- [Blog: How to Automate Enterprise Application Monitoring with Ansible - Part II](http://apmblog.dynatrace.com/2015/04/23/how-to-automate-enterprise-application-monitoring-with-ansible-part-ii/)
- [Slide Deck: Automated Deployments](http://slideshare.net/MartinEtmajer/automated-deployments-slide-share)
- [Slide Deck: Automated Deployments (of Dynatrace) with Ansible](http://www.slideshare.net/MartinEtmajer/automated-deployments-with-ansible)
- [Slide Deck: Testing Ansible Roles with Test Kitchen, Serverspec and RSpec](http://www.slideshare.net/MartinEtmajer/testing-ansible-roles-with-test-kitchen-serverspec-and-rspec-48185017)
- [Tutorials: Automated Deployments (of Dynatrace) with Ansible](https://community.compuwareapm.com/community/display/COE/Tutorials+on+Automated+Deployments#TutorialsonAutomatedDeployments-ansible)

## Questions?

Feel free to post your questions on the Dynatrace Community's [Continuous Delivery Forum](https://community.dynatrace.com/community/pages/viewpage.action?pageId=46628921).

## License

Licensed under the MIT License. See the LICENSE file for details.
[![analytics](https://www.google-analytics.com/collect?v=1&t=pageview&_s=1&dl=https%3A%2F%2Fgithub.com%2FdynaTrace&dp=%2FDynatrace-Collector-Ansible&dt=Dynatrace-Collector-Ansible&_u=Dynatrace~&cid=github.com%2FdynaTrace&tid=UA-54510554-5&aip=1)]()