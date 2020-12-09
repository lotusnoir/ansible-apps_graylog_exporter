# Ansible Role: ansible-apps_graylog_exporter

## Description

[![Build Status](https://travis-ci.com/lotusnoir/ansible-apps_graylog_exporter.svg?branch=master)](https://travis-ci.com/lotusnoir/ansible-apps_graylog_exporter)[![License](https://img.shields.io/badge/license-MIT%20License-brightgreen.svg)](https://opensource.org/licenses/MIT)[![Ansible Role](https://img.shields.io/badge/ansible%20role-apps__graylog_exporter-blue)](https://galaxy.ansible.com/lotusnoir/ansible-apps_graylog_exporter/)[![GitHub tag](https://img.shields.io/badge/version-latest-blue)](https://github.com/lotusnoir/ansible-apps_graylog_exporter/tags)

Deploy [graylog_exporter](https://github.com/boynux/graylog-exporter) to expose graylog metrics to prometheus.

## Role variables

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `graylog_exporter_version` | 0.2.1 | graylog_exporter version |
| `graylog_exporter_install_dir` | /usr/local/bin | directory to install binary |
| `graylog_exporter_force_install` | false | force install variable |
| `graylog_exporter_loglevel` | info | loglevel of exporter |
| `graylog_exporter_graylog_admin` | admin | admin username of graylog |
| `graylog_exporter_graylog_passwd` | admin | admin password of graylog |
| `graylog_exporter_graylog_url` | http://localhost:9000 | port of the graylog service on the graylog server |
| `graylog_exporter_listen_port` | 9122 | port to expose prometheus metrics |

## Examples

	---
	- hosts: apps_graylog_exporter
	  become: yes
	  become_method: sudo
	  gather_facts: yes
	  roles:
	    - role: ansible-apps_graylog_exporter
	  environment: 
	    http_proxy: "{{ http_proxy }}"
	    https_proxy: "{{ https_proxy }}"
	    no_proxy: "{{ no_proxy }}

## License

This project is licensed under Apache License. See [LICENSE](/LICENSE) for more details.
