# CIS Debian 10 Hardening with Ansible
:lock: This project will help you to configure Debian 10 machine to be CIS compliant, based on [cisecurity.org](cisecurity.org) recommendations. With this project the hardening application steps can be more secure, fast and easy, in an automated way using Ansible.

<p align="center">
      <img src="https://user-images.githubusercontent.com/79525895/133907520-c7d4bb80-77e5-4cbc-bd51-c807c05603de.png" width="250px">
</p>

To start using
------------

:warning: NOTE |
--- |
We recomend you to use the Ansible playbooks accompanying with CIS documentation. In this project does not contain all topics from the document, have been removed some default configuration. You too can add or remove tasks as your environment needs. You can contribute with this project helping develop the other topics from the CIS documentation. |

**Hardening Playbook**

To use the Ansible playbooks in your environment you have to edit the **playbook-hardening.yml**.

```bash
---
- name: Execute hardening Debian 10
  hosts: 'GROUP_HOST'
  become: yes
  become_method: sudo
  roles:
    - { role: hardening-debian, tags: ["hardening-debian"]}

```

- ``GROUP_HOST`` : Replace this with your group host from your Ansible inventory.

```bash
$ git clone https://github.com/HailsonJunior/ansible-hardening-debian10.git && cd ansible-hardening-debian10
```

**Running Ansible Hardening Playbook**

To run the playbook you can, for example, use Ansible command like this:

```bash
ansible-playbook -v -u YOUR-USER -i /PATH/YOUR-INVENTORY --limit DEBIAN-HOST -k -K /PATH/playbook-hardening.yml
```

- ``YOUR-USER`` : Replace this with your user name.
- ``/PATH/YOUR-INVENTORY`` : Replace this with the path of your Ansible inventory file.
- ``DEBIAN-HOST`` : Replace this with the name of the Debian host configured in your inventory file.
- ``/PATH/playbook-hardening.yml`` : Replace this with the path of the playbook-hardening.yml file.
