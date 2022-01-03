Role Name
=========

A brief description of the role goes here.

Requirements
------------

Any pre-requisites that may not be covered by Ansible itself or the role should be mentioned here. For instance, if the role uses the EC2 module, it may be a good idea to mention in this section that the boto package is required.

Role Variables
--------------

A description of the settable variables for this role should go here, including any variables that are in defaults/main.yml, vars/main.yml, and any variables that can/should be set via parameters to the role. Any variables that are read from other roles and/or the global scope (ie. hostvars, group vars, etc.) should be mentioned here as well.

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role and tasks (for instance, with variables passed in as parameters) is always nice for users too:

```
---
    - hosts: jitsi
      become: true
      vars_files:
        - /etc/ansible/roles/Jitsi/vars/main.yml
      tasks:

      roles:
        - Jitsi
```


Configuration of role

```
---

    - name: Update apt cache & Upgrade all apt packages
      import_tasks: 1 - update_upgrade.yaml

    - name:  Install dependencies
      import_tasks: 2 - install dependencies.yaml 

    - name:  Install services
      import_tasks: 3 - install_services.yaml 

    - name: Install gnupg2
      import_tasks: 4 - install_gnupg2.yaml 

    - name: Enable appropriate apache2 modules
      import_tasks: 5 - enable_apache2_modules.yaml 

    - name:  Create new configuration file "js.quersys.com.conf"
      import_tasks: 6 - create_file_js.quersys.com.conf.yaml 

    - name:  Create symbolic links "js.quersys.com.conf"
      import_tasks: 7 - create_symbolic_links_js.quersys.com.conf.yaml 

    - name:  Copy cert file js.quersys.com.crt & Copy key file js.quersys.com.key
      import_tasks: 8 - copy_cert_and_key_file.yaml 

    - name:  Generate a key pair for a Shibboleth sp-signing & Generate a key pair for a Shibboleth sp-encrypt     
      import_tasks: 9 - generate_key_pair_Shibboleth.yaml 

    - name: Restart apache service
      import_tasks: 10 - restart_apache.yaml 

    - name:  Create new configuration of shibboleth
      import_tasks: 11 - new_configuration_shibboleth.yaml 

    - name: Restart shibd service.
      import_tasks: 12 - restart_shibd_service.yaml 
      
    - name: Add apt-key for prosody
      import_tasks: 13 - apt-key_apt-repo_prosody.yaml 
      
    - name:  Add apt-key for jitsi
      import_tasks: 14 - apt-key_apt-repo_jitsi.yaml 

    - name: Update and upgrade packages
      import_tasks: 15 - update_upgrade.yaml 

    - name: Configure jitsi-meet package (GUI shell)
      import_tasks: 16 - GUI_dialog_install_jitsi.yaml 

    - name: Install jitsi-meet
      import_tasks: 17 - install_jitsi-meet.yaml 

    - name:  Install jitsi-prosody
      import_tasks: 18 - configuration_prosody.yaml 

    - name: Permissions for "localhost.cnf" & "localhost.crt"
      import_tasks: 19 - change_permission_localhost.cnf_localhost.crt_localhost.key.yaml 

    - name: Copy file quersystem-logo.png
      import_tasks: 20 - copy_image_logo.png.yaml 

    - name:  Configuration Videobridge. Insert a line at the end of a file.
      import_tasks: 21 - configuración_Videobridge_sip.comminicator.yaml 

    - name:  Create new configurationin file "js.quersys.com-config.js"
      import_tasks: 22 - new_configurationin_js.quersys.com-config.js.yaml 

    - name: Configuration of file "all.css". Insert a line at the end of a file.
      import_tasks: 23 - configuration_file_all.css.yaml 

    - name: Ansible multiple replace in file "interface_config.js"
      import_tasks: 24 - replace_data_file_interface_config.js.yaml 

    - name: set of autentication shibboleth
      import_tasks: 25 - autentication_shibboleth.yaml 

    - name: Next number of shard (shard-1, shard-2 etc)script and edit sip-communicator file
      import_tasks: 26 - Next_number_of_shard_script_and_edit_sip-communicator.yaml

    - name: Restart multiple services in a loop
      import_tasks: 27 - restart_multiple_services.yaml 
```

Example host
----------------

[jitsi_server]
jitsi ansible_host=89.108.88.37

[jitsi_jvbs]
jvb1 ansible_host=194.58.92.102

[jitsi_servers:children]
jitsi_server
jitsi_jvbs


License
-------

BSD

Author Information
------------------

Oleg Sidokhmetov.
