Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

coredns_version: 1.14.3
coredns_dist: https://github.com/coredns/coredns/releases/download/v{{coredns_version}}/coredns_{{coredns_version}}_linux_amd64.tgz

coredns_dir: /opt/coredns
coredns_config_dir: /etc/coredns
coredns_config_dir_zone: "{{ coredns_config_dir }}/zones"

coredns_user: coredns
coredns_firewalld_service_zone: public

coredns_service_name: "coredns"
coredns_service_file: "/etc/systemd/system/{{ coredns_service_name }}.service"

coredns_service_log: "/var/log/coredns"

# SERVER defaults:
coredns_port: 53

# Zone
coredns_zone_master: ""
coredns_zone_secondary: 
  host:
    domain_name: org
    master_ip: 1.1.1


Dependencies
------------


Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: core-dns
      remote_user: vagrant
      become: yes
      roles:
         - coredns

License
-------

BSD

