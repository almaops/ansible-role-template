aboveops.template
=========

Create file from template

Description
-----------

You can think about this role as about a wrapper for the template ansible module.

Just provide it with a template and get a result written to some file on the target system.

Example
-------

    - role: aboveops.template
      template_content: |
        upstream grafana {
            {% for host in groups["monitoring"] %}
            server {{ hostvars[host].backnet_ip }}:3000;
            {% endfor %}
        }
      template_dest: "/etc/nginx/conf.d/grafana_upstream.conf"

Install
-------

This role can be installed from [Ansible Galaxy](https://galaxy.ansible.com/):

`ansible-galaxy install aboveops.template`

License
-------

MIT

Author Information
------------------

Dmitrii Kashin, <freehck@freehck.com>
