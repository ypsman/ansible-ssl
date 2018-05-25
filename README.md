ansible ssl
===========
[![Build Status](https://travis-ci.org/ypsman/ansible-ssl.svg?branch=master)](https://travis-ci.org/ypsman/ansible-ssl)

Installs SSL Cert and Key on your Server.<br>
Chainfile will only Copied if defined.


defaults:
---------
    ssl_cert_path:    '/etc/ssl/certs'
    ssl_key_path:     '/etc/ssl/private'
    ssl_crt_name:     'server.crt'
    ssl_key_name:     'server.key'
    ssl_ica_name:     'server.ca'
    ssl_user:         'root'
    ssl_group:        'root'
    ssl_cert_umask:   '0644'
    ssl_key_umask:    '0640'

You can override the Defaults in youre Playbook

Example Playbook
----------------

    - hosts: all
      roles:
        - role: ypsman.ssl
          ssl_cert: vars/certfile.crt
          ssl_key:  vars/certfile.key
          ssl_ica:  vars/chainfile.pem    # optional 
          ssl_cert_path: '/etc/pki/certs' # optional
