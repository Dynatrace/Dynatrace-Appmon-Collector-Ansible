# Dynatrace-Collector-Ansible

This Ansible role installs and configures the Dynatrace Collector of the [Dynatrace AppMon](https://www.dynatrace.com/support/doc/appmon/) solution.

## Download

The role is available via:

- [Ansible Galaxy](https://galaxy.ansible.com/Dynatrace/Dynatrace-Collector)
- [GitHub](https://github.com/Dynatrace/Dynatrace-Collector-Ansible)

## Description

This role downloads and installs the most recent version of the Dynatrace Collector from [http://downloads.dynatracesaas.com](http://downloads.dynatracesaas.com). Alternatively, you can place the installer artifact as `dynatrace-collector-linux-x86.jar` in the role's `files` directory from where it will be picked up during the installation. The default file name and URL can be overridden via the `dynatrace_collector_linux_installer_file_name` and `dynatrace_collector_linux_installer_file_url` attributes, respectively. Please refer to `defaults/main.yml` for a list of supported attributes.

## Role Variables

As defined in ```defaults/main.yml```:

| Name                                            | Default                                                                  | Description |
|-------------------------------------------------|--------------------------------------------------------------------------|-------------|
| *dynatrace_collector_installer_bitsize*         | 64                                                                       | 32 or 64 |
| *dynatrace_collector_linux_install_dir*         | /opt                                                                     | The Dynatrace Collector will be installed into the directory *$dynatrace_collector_linux_install_dir*/dynatrace-*$major*-*$minor*-*$rev*, where *$major*, *$minor* and *$rev* are given by the installer. A symbolic link to the actual installation directory will be created in *$dynatrace_collector_linux_install_dir*/dynatrace. |
| *dynatrace_collector_linux_installer_file_name* | dynatrace-collector-7.2.0.1697-linux-x86.jar                             | The file name of the Dynatrace Collector installer in the role's ```files``` directory. |
| *dynatrace_collector_linux_installer_file_url*  | https://files.dynatrace.com/downloads/OnPrem/dynaTrace/7.2/7.2.0.1697/dynatrace-collector-7.2.0.1697-linux-x86.jar | A HTTP, HTTPS or FTP URL to the Dynatrace Collector installer in the form (http\|https\|ftp)://[user[:pass]]@host.domain[:port]/path. |
| *dynatrace_collector_agent_port*                | 9998                                                                     | The port where the Collector shall listen for agent connections. |
| *dynatrace_collector_server_hostname*           | localhost                                                                | The location of the Server the Collector shall connect to. |
| *dynatrace_collector_server_port*               | 6699                                                                     | The port on the Server the Collector shall connect to. Use either ```6698``` (non-SSL) or ```6699``` (SSL). |
| *dynatrace_collector_jvm_xms*                   |                                                                          | The Dynatrace Collector's JVM setting: -Xms. |
| *dynatrace_collector_jvm_xmx*                   |                                                                          | The Dynatrace Collector's JVM setting: -Xmx. |
| *dynatrace_collector_jvm_perm_size*             |                                                                          | The Dynatrace Collector's JVM setting: -XX:PermSize. |
| *dynatrace_collector_jvm_max_perm_size*         |                                                                          | The Dynatrace Collector's JVM setting: -XX:MaxPermSize. |
| *dynatrace_collector_owner*                     | dynatrace                                                                | The system user that owns the Dynatrace installation.
| *dynatrace_collector_group*                     | dynatrace                                                                | The system user's group that owns the Dynatrace installation.
| *dynatrace_collector_role_name*                 | Dynatrace.Dynatrace-Collector                                            | The actual name of this role in an [Ansible Playbook's](http://docs.ansible.com/playbooks.html) ```roles``` directory. |

## Example Playbook

```
- hosts: all
  roles:
    - role: Dynatrace.Dynatrace-Collector
```

## Testing

We use [Test Kitchen](http://kitchen.ci) to automatically test our automated deployments with [Serverspec](http://serverspec.org) and [RSpec](http://rspec.info/):

1) Install Test Kitchen and its dependencies from within the project's directory:

```
gem install bundler
bundle install
```

2) Run all tests

```
kitchen test
```

By default, we run our tests inside [Docker](https://www.docker.com/) containers as this considerably speeds up testing time (see `.kitchen.yml`).

## Additional Resources

### Blogs

- [How to Automate Enterprise Application Monitoring with Ansible](http://apmblog.dynatrace.com/2015/03/04/how-to-automate-enterprise-application-monitoring-with-ansible/)
- [How to Automate Enterprise Application Monitoring with Ansible - Part II](http://apmblog.dynatrace.com/2015/04/23/how-to-automate-enterprise-application-monitoring-with-ansible-part-ii/)

### Presentations

- [Automated Deployments (of Dynatrace) with Ansible](http://www.slideshare.net/MartinEtmajer/automated-deployments-with-ansible)
- [Test-Driven Infrastructure with Ansible, Test Kitchen, Serverspec and RSpec](http://www.slideshare.net/MartinEtmajer/testing-ansible-roles-with-test-kitchen-serverspec-and-rspec-48185017)

## Problems? Questions? Suggestions?

This offering is [Dynatrace Community Supported](https://community.dynatrace.com/community/display/DL/Support+Levels#SupportLevels-Communitysupported/NotSupportedbyDynatrace(providedbyacommunitymember)). Feel free to share any problems, questions and suggestions with your peers on the Dynatrace Community's [Application Monitoring & UEM Forum](https://answers.dynatrace.com/spaces/146/index.html).

## License

Licensed under the MIT License. See the LICENSE file for details.
[![analytics](https://www.google-analytics.com/collect?v=1&t=pageview&_s=1&dl=https%3A%2F%2Fgithub.com%2FdynaTrace&dp=%2FDynatrace-Collector-Ansible&dt=Dynatrace-Collector-Ansible&_u=Dynatrace~&cid=github.com%2FdynaTrace&tid=UA-54510554-5&aip=1)]()
