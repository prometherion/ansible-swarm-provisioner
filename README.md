# swarm-provisioner
Just a simple Ansible playbook in order to do provisioning of Docker Swarm nodes on AWS.



## Why?

I'm setting up a Docker Swarm Cluster inside AWS and I need do all the basic stuff with specifici constraints related to
cluster types. I could do all that kind of stuff with simple bash scripts using the AWS EC2 User Data: by the way I
wanted to practicing with Ansible and... here we are!



## How to use

##### Setting up a master

Just run the playbook with the command `ansible-playbook -i hosts -c local master.yml -e engine_role={YOUR_ROLE}`.

 - `engine_role`: refers to Docker engine label you would like to attach to node: maybe you want to keep tidy and clean
                  your master node avoiding the run of production containers.

Remember to keep somewhere the swarm token and address listener in order to enable worker join!

##### Setting up a worker

Just run the playbook with the command `ansible-playbook -i hosts -c local worker.yml -e engine_role={YOUR_ROLE} -e
token={SWARM_TOKEN} -e address={SWARM_ADDRESS}`.

 - `engine_role`: refers to Docker engine label you would like to attach to node: this is useful to create constraints
                  over cluster groups (you can run only some kinds of services over a specific Auto Scaling Group, maybe
                  for performances or in order to make easier the scale down of a service).
 
 - `token`: the Swarm cluster Token obtained via Master election.
  
 - `address`: the Swarm cluster master address obtained via Master election.



### Dependencies
In case of provisioning Python and PIP should be already installed in order to download and setup Ansible.



### JFI
The Ansible Playbook is optimized for AWS Linux distribution based on `YUM` package manager: you can edit in order to
use `apt` or whatever you want: feel free to PR!