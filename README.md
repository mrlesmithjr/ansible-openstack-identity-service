<!-- START doctoc generated TOC please keep comment here to allow auto update -->
<!-- DON'T EDIT THIS SECTION, INSTEAD RE-RUN doctoc TO UPDATE -->
**Table of Contents**  *generated with [DocToc](https://github.com/thlorenz/doctoc)*

- [ansible-openstack-identity-service](#ansible-openstack-identity-service)
  - [Requirements](#requirements)
  - [Role Variables](#role-variables)
  - [Dependencies](#dependencies)
    - [Ansible Roles](#ansible-roles)
  - [Example Playbook](#example-playbook)
  - [License](#license)
  - [Author Information](#author-information)

<!-- END doctoc generated TOC please keep comment here to allow auto update -->

# ansible-openstack-identity-service

An [Ansible](https://www.ansible.com) role to install/configure [OpenStack Identity Services](https://docs.openstack.org/ocata/install-guide-ubuntu/common/get-started-identity.html)

## Requirements

None

## Role Variables

```yaml
---
# defaults file for ansible-openstack-identity-service

# Defines the default OpenStack admin user info
# Generate password with:
# openssl rand -hex 10
openstack_identity_service_admin_info:
  pass: []
  user: 'admin'
  admin_url: '{{ openstack_identity_service_keystone_endpoint_url }}:35357/v3/'
  internal_url: '{{ openstack_identity_service_keystone_endpoint_url }}:5000/v3/'
  public_url: '{{ openstack_identity_service_keystone_endpoint_url }}:5000/v3/'
  region_id: 'RegionOne'

# Defines Keystone DB info
openstack_identity_service_keystone_db_info:
  db: 'keystone'
  pass: 'keystone'
  host: 'localhost'
  user: 'keystone'

# Defines the default Keystone endpoint url
# Do not append the port or api version
openstack_identity_service_keystone_endpoint_url: 'http://{{ inventory_hostname }}'
```

## Dependencies

### Ansible Roles

The following [Ansible](https://www.ansible.com) roles are required as part of
this role.

-   [ansible-chrony](https://github.com/mrlesmithjr/ansible-chrony)
-   [ansible-config-interfaces](https://github.com/mrlesmithjr/ansible-config-interfaces)
-   [ansible-etc-hosts](https://github.com/mrlesmithjr/ansible-etc-hosts)
-   [ansible-memcached](https://github.com/mrlesmithjr/ansible-memcached)
-   [ansible-mysql](https://github.com/mrlesmithjr/ansible-mysql)
-   [ansible-openstack-base](https://github.com/mrlesmithjr/ansible-openstack-base)
-   [ansible-openstack-openrc](https://github.com/mrlesmithjr/ansible-openstack-openrc)
-   [ansible-rabbitmq](https://github.com/mrlesmithjr/ansible-rabbitmq)

The above roles can be installed using `ansible-galaxy` along with [requirements.yml](./requirements.yml):

```bash
ansible-galaxy install -r requirements.yml
```

## Example Playbook

[Example Playbook](./playbook.yml)

## License

MIT

## Author Information

Larry Smith Jr.

-   [@mrlesmithjr](https://www.twitter.com/mrlesmithjr)
-   [EverythingShouldBeVirtual](http://www.everythingshouldbevirtual.com)
-   mrlesmithjr [at] gmail.com
