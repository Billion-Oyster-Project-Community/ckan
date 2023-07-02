# ckan
Infrastructure &amp; Automation tooling for deploying ckan.

To run this playbook

```bash
ansible-playbook -K -i inventory.yml ckan.yml
```

## Project Status

Production ready: ❌

Currently this role is not production ready. It will provide a basic single-node ckan installation and nothing else.

TODO:

- Secure port access.
- Create a dedicated ckan user.
- Remove redundant dependencies.
- Add handlers for supervisorctl, supervisor, nginx, solr, and ckan.
- Add ckan version variable.
- ckan extensions.
- 100% ansible-lint.

## Future Features

This project is not intended to only be a ckan role. In the future Azure Virtual Machine support, remote postgres, Ceph,  and other high availability features are planned to be added.