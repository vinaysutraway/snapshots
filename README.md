## Documentation
http://docs.ansible.com/ansible/latest/vmware_guest_snapshot_module.html

https://www.justai.net/en/blog/using-ansible-to-manage-vmware-infrastructure/

## Requirements (on host that executes module)
python >= 2.6
PyVmomi

## Before starting
Virtual Machines will need to be in a folder, This can be done on the GUI, folder then must be entered into the vars/vars_file.

Populate vars/vars_file.yml example:
```
---
  datacenter: ""
  hostname: ""
  username: ""
  password: ""
  snapshot_name: ""
  snapshot_description: ""
  machines: "{{ inventory_hostname }}"

```

Then encrypt it,
```
# ansible-vault encrypt vars/vars_file
New Vault password:
Confirm New Vault password:
Encryption successful
```

## How to use
Once vars/vars_file.yml has been populated, you want to start by testing and getting facts about your VM's.
```
# ansible-playbook -i inventory -l group guestfacts.yml --ask-vault-pass
```
