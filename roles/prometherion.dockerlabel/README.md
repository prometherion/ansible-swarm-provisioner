Packages
=========
Just a simple role in order to add labels to Docker Engine.

Requirements
------------
Docker should be installed and started in order to get configuration files already available.

Role Variables
--------------
 - `engine_role` the application module role

Dependencies
------------
None

Example Playbook
----------------
    - hosts: servers
      roles:
         - { role: "prometherion.dockerlabel", engine_role: "api" }

License
-------
BSD

Author Information
------------------
Dario Tranchitella (prometherion)
<dario@tranchitella.eu>
