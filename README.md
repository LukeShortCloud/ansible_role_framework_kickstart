# ansible_role_framework_kickstart

Create Anaconda Kickstart files using Ansible and Jinja templating. Available options for Kickstart can be found [here](https://pykickstart.readthedocs.io/en/latest/kickstart-docs.html).

## Requirements

None.

## Dependencies

None.

## Variables

* framework_kickstart_tmp_dir = The directory the Kickstart file is saved to.
* framework_kickstart_file_name = The file name of the Kickstart file.
* ks_url = The URL to download the operating system kernel and packages from.
* ks_lang = The language to setup.
* ks_keyboard = The keyboard layout.
* ks_timezone = The timezone.
* ks_drive = The primary drive letter. This usually should not be changed.
* ks_autopart_enable = If autopartitioning should be used.
* ks_autopart_type = The autopartitioning layout to use.
* ks_partitions = A list of partition descriptions.
* ks_rootpw = The root password for the virtual machine.
* ks_selinux_enable = Enable SELinux.
* ks_networks = A list of networks to setup.
* ks_firewall_enable= Enable firewalld.
* ks_firewall = Options for the firewalld service.
* ks_packages = A list of packages to install.
* ks_services_disabled = Services to disable.
* ks_services_enabled = Services to enable.

## Example Playbook

```
---
- hosts: localhost
  roles:
    - name: ansible_role_framework_kickstart
      vars:
        ks_packages:
          - "@core"
          - "@Virtualization Host"
          - curl
          - vim
```

## License

Apache v2.0
