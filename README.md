ansible ssl
===========
[![Build Status](https://travis-ci.org/ypsman/ansible-ssl.svg?branch=master)](https://travis-ci.org/ypsman/ansible-ssl)

Installs SSL Cert and Key on your Server.

defaults:
---------
    ssl_cert_path:    '/etc/ssl/local'    # Path to install
    ssl_crt_name:     'server.crt'        # name of the crt File
    ssl_key_name:     'server.key'        # name of the Key File
    ssl_user:         'root'              # Owner of Files
    ssl_group:        'root'              # Group Owner
    ssl_umask:        '0400'              # umask for Folder and Files

You can override the Defaults in youre Playbook

Example Playbook
----------------

    - hosts: all
      roles:
        - role: ypsman.ssl
          ssl_cert: |
                    --- SSL CERT---
                    1234567890abcdef
                    1234567890abcdef
                    1234567890abcdef
                    1234567890abcdef
                    --- END CERT ---
          ssl_key:  |
                    ---- SSL KEY ---
                    1234567890abcdef
                    1234567890abcdef
                    1234567890abcdef
                    1234567890abcdef
                    ---- END Key ---
          ssl_cert_path:    '/etc/ssl/local'  # Optional for other Path
