# Ansible Openresty

[![Build Status](https://travis-ci.org/quantmind/ansible-openresty.svg?branch=master)](https://travis-ci.org/quantmind/ansible-openresty)

[![CircleCI](https://circleci.com/gh/quantmind/ansible-openresty.svg?style=svg)](https://circleci.com/gh/quantmind/ansible-openresty)

[![galaxy](https://img.shields.io/badge/galaxy-quantmind.openresty-blue.svg)](https://galaxy.ansible.com/quantmind/openresty/)


Ansible role to create an openresty docker image and add configuration files.

## Create Image

To create an image the ``openresty_image_name`` must be a string for the image name.
An example playbook:
```yaml
- name: Create the docker image for openresty

  hosts: nginx

  vars:
    openresty_image_name: openresty

  roles:
    - openresty

```

## Install sites

When ``openresty_image_name`` is set to ``false`` (the default value), the role installs

* Nginx configuration files for web sites in ``openresty_volume_nginx_config_path``
* SSL server certificates in ``openresty_volume_nginx_ssl_path``
* Html/static assets in ``openresty_volume_nginx_html_path``

### Configuration files

These are defined in the ``services`` list. The list containes objects with
schema::
```json
{
}
```

