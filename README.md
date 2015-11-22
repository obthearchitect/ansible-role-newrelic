# ansible-role-newrelic

This ansible role installs and configures the New Relic Server Agent (System Monitor Daemon) for Ubuntu 14.04.3 Trusty. 

## Requirements

This role requires Ansible 1.4 higher and platforms listed in the metadata file.

## Role Variables

The variables defined in `defaults/main.yml` can be passed configured and passed through for a customized installation. 

    # License key
    newrelic_license_key: YOUR_KEY_HERE
    
    # Log level (error, warning, info, verbose, debug, verbosedebug)
    newrelic_loglevel: info
    
    # Log file location
    newrelic_logfile: /var/log/newrelic/nrsysmond.log
    
    # Proxy server. Default False
    newrelic_proxy: fred:secret@proxy.mydomain.com:8181
    
    # Use SSL for all communication. Default False
    newrelic_ssl: "true"
    
    # SSL CA Bundle path. Default False
    newrelic_ssl_ca_bundle: /etc/pki/tls/certs/ca-bundle.crt
    
    # SSL CA Path. Default False
    newrelic_ssl_ca_path: /etc/ssl/certs
    
    # Pid file locaiton
    newrelic_pidfile: /var/run/newrelic/nrsysmond.pid
    
    # Collector hostname
    newrelic_collector_host: collector.newrelic.com
    
    # Connection timeout for collector host
    newrelic_timeout: 30

## Examples

### Paramaterized Role
You can pass in your license key from the `roles` section in your main playbook in JSON format. For example:

    ---
    - hosts: all
      roles:
        - { role: newrelic, newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16 }

### Vars
You can pass in your license key from the `vars` section in your main playbook. For example:

    ---
    - hosts: all
      vars:
        newrelic_license_key: ab2fa361cd4d0d373833cad619d7bcc424d27c16
      roles:
        - newrelic

#### site.yml

    ---
    - hosts: all
      roles:
        - newrelic## Role Name

## License
This build is released under the MIT license.

## Author Information
Ovidio Borrero