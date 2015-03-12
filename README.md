gunicorn-config
================

Generate config files for gunicorn.

Requirements
------------

None

Role Variables
--------------
Variables with default values ( selfexplanatory ) :

    gunicorn_conf_output_file: '/tmp/gunicorn.py'

    gunicorn_conf_bind: '127.0.0.1'
    gunicorn_conf_workers: 'multiprocessing.cpu_count() * 2 + 1'
    gunicorn_conf_user: {{ remote_user }}

    gunicorn_conf_logfile: '/var/log/gunicorn.log'
    gunicorn_conf_loglevel: 'info'

    gunicorn_conf_pidfile: '/tmp/gunicorn.pid'

    gunicorn_conf_daemon: 'False'
    gunicorn_conf_debug: 'False'
    gunicorn_conf_timeout: '300'


Dependencies
------------

None

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: jcsaaddupuy.gunicorn_config, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
