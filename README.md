# ckan
Infrastructure and Automation tooling for deploying ckan.

To run this playbook

```bash
ansible-playbook -K -i inventory.yml ckan.yml
```

## Project Status

This role can be used to deploy a single node instance of ckan. It is recommended to configure a reverse proxy for ssl termination. If a remote database is being used replace `postgres_host` with the remote hosts address in `inventory.yml`.

## Future Features

This project is not intended to only be a ckan role. In the future AWS EC2 support, remote postgres (RDS), Ceph,  and other high availability features are planned to be added.

## Basic Administration
**Creating a Sysadmin user**
```bash
sudo -u www-data /usr/lib/ckan/default/bin/ckan -c /etc/ckan/default/ckan.ini sysadmin add admin name=admin
```
**Xloader configuration**
1. Login as an admin user
1. Go to API Tokens
1. Create an API token for xloader
2. Insert the API token into `inventory.yml`
```yml
xloader_api_token: API_TOKEN
```

## Role Usage
| Variable            | Description                                                                                                |
| ------------------- | ---------------------------------------------------------------------------------------------------------- |
| `fqdn` | The fully qualified domain name of the target host.                                                                     |
| `ckan_version` | The ckan installation version. **Only supported version is 2.10+**                                              |
| `postgres_host` | The address of the PostgreSQL instance.                                                                        |
| `postgres_password` | The `postgres` user master password alongside with the user password for the `ckan_default` postgres user. |
| `xloader_api_token` | API Token for https://github.com/ckan/ckanext-xloader                                                      |
| `plugins` | ckan plugins that are to be loaded into ckan on startup. `xloader` & `datastore` (required) are installed by default.|

## Contributing

This project uses Vagrant as the primary method to test this Ansible playbook.

Set the virtualization provider.
```bash
export VAGRANT_DEFAULT_PROVIDER=libvirt
```
Set the default network interface to use for the bridge.
```ruby
# Vagrantfile
DEFAULT_NETWORK_INTERFACE = "eth1"
```
Start the virtual machine.
```bash
vagrant up
```

