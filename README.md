Ansible Role: Thales Vormetric Transparent Encryption agent
=========

Ansible role to install [Thales Vormetric Transparent Encryption](https://www.thalestct.com/Solutions/Enterprise-Security/data-encryption/Vormetric%20Data%20at%20Rest%20Encryption/vte/index.html) agent on Linux Servers.

Requirements
------------

The role does not require anyting to run on RHEL and its derivatives. This role assumes that you have the software package located on a web server somewhere in your environment.

Role Variables
--------------

Available variables are listed below, along with default values ```(see defaults/main.yml)```:

```
software_url: "http://www.example.org"
package_base_name: "vee-fs"
package_version: "6.3.1-82"
dsm_hostname: "mydsm.example.org"
host_domain: "dsm_domain"
registration_secret: "mystrongpass"
```

```software_url``` **(Required)** The URL that hosts the Installer package. This should be either **http** or **https**.

```package_base_name``` **(Required)** The Installer package base (or begining) name. Unless Thales changes this in the future, should allways be **vee-fs**

```package_version``` **(Required)** The version of the installer package. Agents are updated from time to time, so this var can be overridden with the latest version.

```dsm_hostname``` **(Required)** The fully-qualified hostname (or IP address) of the Data Security Manager (DSM) appliance.

```host_domain``` **(Required)** The Domain to attach newly registered agents. This name will have to match exactly how it is created in the DSM.

```registration_secret``` **(Required)** The shared password used for automatic registration of agents to the DSM.

Role variables can be stored with the hosts.yaml file, or in the main variables file.

Dependencies
------------

None.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - role: mikepruett3.vormetric-agent
           vars:
             software_url: "http://www.example.org"
             package_base_name: "vee-fs"
             package_version: "6.3.1-82"
             dsm_hostname: "mydsm.example.org"
             host_domain: "dsm_domain"
             registration_secret: "mystrongpass"

License
-------

MIT

Author Information
------------------

Role created by [mikepruett3](https://github.com/mikepruett3) on [Github.com](https://github.com/mikepruett3)
