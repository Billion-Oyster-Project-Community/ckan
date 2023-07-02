# ckan
Infrastructure &amp; Automation tooling for deploying ckan.

To run this playbook

```bash
ansible-playbook -K -i inventory.yml ckan.yml
```

<h3>Todo:</h3>

<u>Ckan</u>
- Configuration files
    - uWSGI
- supervisord

<u>Nginx</u>
- proxy

<u>PostgreSQL</u>
- ckan_default database ✅

<u>Apache Solr</u>

<u>Redis</u> ✅

<u>Ckan extensions</u>
- xloader
- datastore

