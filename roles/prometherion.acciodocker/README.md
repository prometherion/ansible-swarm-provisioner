Packages
=========
Just a simple role in order to update and install Docker using YUM.

Requirements
------------
This role is  designer for AWS Linux distribution based on `YUM` package manager: you can edit in order to use `apt` or
whatever you want: feel free to PR!

Role Variables
--------------
None

Dependencies
------------
None

Example Playbook
----------------
    - hosts: servers
      roles:
         - { role: prometherion.acciodocker }

License
-------
BSD

Author Information
------------------
Dario Tranchitella (prometherion)
<dario@tranchitella.eu>
