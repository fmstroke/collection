# Ansible Collection - nomakcooper.collection
![collection](https://img.shields.io/badge/ansible-collection-blue?style=flat-square&logo=ansible&logoColor=white)
![automation](https://img.shields.io/badge/ansible-automation-blue?style=flat-square&logo=ansible&logoColor=white)
![galaxy](https://img.shields.io/badge/ansible-galaxy-blue?style=flat-square&logo=ansible&logoColor=white)
![module](https://img.shields.io/badge/ansible-module-blue?style=flat-square&logo=ansible&logoColor=white)
![roles](https://img.shields.io/badge/ansible-roles-blue?style=flat-square&logo=ansible&logoColor=white)

## Documentation for the collection.
* This collection includes some custom modules developed by [@NomakCooper](https://github.com/NomakCooper).
### How to use this collection and module

* collection install :
```bash
$ ansible-galaxy collection install nomakcooper.collection
```
* [**Recommended**] install dependences **role** ( required for charts module ):
```yaml
  - name: Install Dependencies on CN
    hosts: all
    gather_facts: no
    roles:
      - role: nomakcooper.collection.install_dep
```
```yaml
  - name: Install Dependencies on CN
    hosts: all
    gather_facts: no

    pre_tasks:

      - name: install dependencies
        block:
          - include_role:
              name: nomakcooper.collection.install_dep
        become: false
```
* install dependences ( required for charts module ):
```bash
# Ansible Core requirements.txt
$ pip install -r ~/.ansible/collections/ansible_collections/nomakcooper/collection/meta/requirements.txt
```
```bash
# AWX/Tower requirements.txt
$ pip install -r /var/lib/awx/venv/ansible/meta/requirements.txt
```
```bash
# Ansible Core install_dependencies.yml
$ ansible-playbook install_dependencies.yml
```
* module usage :
```yaml
- name: Retrieve load average for today
  nomakcooper.collection.sar_facts:
    type: "load"
```


