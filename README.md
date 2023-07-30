# ansible-servers
This is my playbook to configure the basic stuff in my servers

## Instructions
### Prerequisites and basic test
1. Configure ssh-key access to the servers
1. Add ssh identyties to your ssh-agent
1. [Install ansible](https://docs.ansible.com/ansible/latest/installation_guide/intro_installation.html)
1. Create yout hosts inventory, or global one in `/etc/ansible/hosts` or a local one. As an example:
    ```
    [all]
    192.168.1.254
    192.168.1.253
    ```
1. Run the following to clarify if the server is working with ansible:
    ```
    ansible -i hosts all -u <user in the server> -m ping
    ```
    At this point, if all is working fine, you will se this:
    ```
    192.168.1.254 | SUCCESS => {
        "ansible_facts": {
            "discovered_interpreter_python": "/usr/bin/python3"
        },
        "changed": false,
        "ping": "pong"
    }  
    ```
### Run the playbook
`ansible-playbook -i <inventory> -u <user> -K main.yaml`