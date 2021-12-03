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
- hosts: nameofhost
  become: true
  vars_files:
    - /etc/ansible/roles/Jitsi/vars/main.yml
  tasks:

    - name: Update apt cache & Upgrade all apt packages
      include: 1update_upgrade.yaml

    - name:  Install dependencies
      include: 2install dependencies.yaml 

    - name:  Install services
      include: 3install_services.yaml 

    - name: install gnupg2
      include: 4install_gnupg2.yaml 

    - name: Enable appropriate apache2 modules
      include: 5enable_apache2_modules.yaml 

    - name:  Create new configuration file "js.quersys.com.conf"
      include: 6create_file_js.quersys.com.conf.yaml 

    - name:  Create symbolic links "js.quersys.com.conf"
      include: 7create_symbolic_links_js.quersys.com.conf.yaml 

    - name:  Copy cert file js.quersys.com.crt & Copy key file js.quersys.com.key
      include: 8copy_cert_and_key_file.yaml 

    - name:  Generate a key pair for a Shibboleth sp-signing & Generate a key pair for a Shibboleth sp-encrypt     
      include: 9generate_key_pair_Shibboleth.yaml 

    - name: Restart apache service
      include: 10restart_apache.yaml 

    - name:  Create new configuration of shibboleth
      include: 11new_configuration_shibboleth.yaml 

    - name: Restart shibd service.
      include: 12restart_shibd_service.yaml 
      
    - name: Add apt-key for prosody
      include: 13apt-key_apt-repo_prosody.yaml 
      
    - name:  Add apt-key for jitsi
      include: 14apt-key_apt-repo_jitsi.yaml 

    - name: update and upgrade packages
      include: 15update_upgrade.yaml 

    - name: Configure jitsi-meet package (GUI shell)
      include: 16GUI_dialog_install_jitsi.yaml 

    - name: install jitsi-meet
      include: 17install_jitsi-meet.yaml 

    - name:  install jitsi-prosody
      include: 18configuration_prosody.yaml 

    - name: permissions for "localhost.cnf" & "localhost.crt"
      include: 19change_permission_localhost.cnf_localhost.crt_localhost.key.yaml 

    - name: Copy file quersystem-logo.png
      include: 20copy_image_logo.png.yaml 

    - name:  Configuration Videobridge. Insert a line at the end of a file.
      include: 21configuración_Videobridge_sip.comminicator.yaml 

    - name:  Create new configurationin file "js.quersys.com-config.js"
      include: 22new_configurationin_js.quersys.com-config.js.yaml 

    - name: Configuration of file "all.css". Insert a line at the end of a file.
      include: 23configuration_file_all.css.yaml 

    - name: Ansible multiple replace in file "interface_config.js"
      include: 24replace_data_file_interface_config.js.yaml 

    - name: set of autentication shibboleth
      include: 25autentication_shibboleth.yaml 

    - name: Next number of shard (shard-1, shard-2 etc)script and edit sip-communicator file
      include: 26Next_number_of_shard_script_and_edit_sip-communicator.yaml

    - name: Restart multiple services in a loop
      include: 27restart_multiple_services.yaml 
```

License
-------

BSD

Author Information
------------------

Oleg Sidokhmetov.
