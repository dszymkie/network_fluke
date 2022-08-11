Network_fluke
=========

Implementation/configuration of network_fluke

Role Variables
--------------

### Inventory global vars:
```yaml
    # HOSTS ALL
    hosts_all:
      vars:
        become: true
        become_method: sudo
```

### Inventory localhost vars:
```yaml
    # LOCALHOST
    localhost:
      ansible_connection: local
```

### Playbooks/network_fluke.yml vars:
```yaml
      - hosts: localhost
        gather_facts: true
        ignore_errors: true
```

Dependencies
------------

```python
roles/requirements.yml
```
```yaml
    - collections:

      - community.general
```

Playbooks/network_fluke.yml
----------------

```yaml
    - hosts: localhost
      gather_facts: true
      ignore_errors: true

      roles:
        - role:
            network_fluke
```

Deployment
------------

```python
# Deployment
ansible-playbook playbooks/network_fluke.yml -i inventory/hosts
```
