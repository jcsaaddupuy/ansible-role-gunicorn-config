gunicorn-config
================

Generate config files for gunicorn.

Requirements
------------

None

Role Variables
--------------
Variables with default values ( self-explanatory ) :

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

Assuming you have a variable 'app_name' with value 'myapp' :

    - hosts: servers
      vars:
          - gunicorn_conf_user: "{{app_name}}"
          - gunicorn_conf_output_file: '/tmp/{{app_name}}-gunicorn.py'

          - gunicorn_conf_bind: '127.0.0.1'
          - gunicorn_conf_workers: 'multiprocessing.cpu_count() * 2 + 1'
          - gunicorn_conf_logfile: '/var/log/{{app_name}}-gunicorn.log'
          - gunicorn_conf_loglevel: 'info'

          - gunicorn_conf_pidfile: '/tmp/{{app_name}}-gunicorn.pid'

          - gunicorn_conf_daemon: 'False'
          - gunicorn_conf_debug: 'False'
          - gunicorn_conf_timeout: '200'
      roles:
         - role: jcsaaddupuy.gunicorn_config

Will generate the following file in /tmp/myapp-gunicorn.py :

    import multiprocessing

    bind = "127.0.0.1"
    workers = multiprocessing.cpu_count() * 2 + 1
    user = 'myapp'
    logfile = "/var/log/myapp-gunicorn.log"
    loglevel = "info"
    pidfile = '/tmp/myapp-gunicorn.pid'
    daemon = False
    debug = False
    timeout = 200




License
-------

BSD

Author Information
------------------
Missing config key ? please make a PR :)

[github/jcsaaddupuy](https://github.com/jcsaaddupuy/)
