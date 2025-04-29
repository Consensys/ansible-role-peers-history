# Ansible Role: peers_history

### Description
Ansible role that will install, configure and runs [peers_history](https://github.com/Consensys/peers-history)

### Table of Contents
  - [Supported Platforms](#supported-platforms)
  - [Dependencies](#dependencies)
  - [Role Variables](#role-variables)
  - [Example Playbook](#example-playbook)
  - [License](#license)
  - [Author Information](#author-information)

### Supported Platforms
```
* Debian
* Ubuntu
* Redhat(CentOS/Fedora)
* Amazon
```

### Dependencies

* JDK 11 or greater

### Role Variables:

All variables which can be overridden are stored in [defaults/main.yml](defaults/main.yml) file. By and large these variables are configuration options. Please refer to [peers_history](https://github.com/Consensys/peers-history) for more information

| Name           | Default Value | Description                        |
| -------------- | ------------- | -----------------------------------|
| `peers_history_version` | "v1.0.0" | Version to use              |
| `peers_history_rpc_url` | "http://localhost:8545" | URL to scrape   |
| `peers_history_scrape_interval` | 15 | Scrape interval |
| `peers_history_ttl` | 365 | TTL in days   |
| `peers_history_keep_alive_log_interval` | 300 | Max interval between 2 logs |
| `peers_history_verbose` | true | enable verbose logs   |
| `peers_history_cmdline_args` | [] | extra cmd line args   |

### Example Playbook

1. Default setup:
Install the role from galaxy
```
ansible-galaxy install consensys.peers_history
```

Create a requirements.yml with the following:
Replace `x.y.z` below with the version you would like to use 
```
---
- hosts: localhost
  connection: local
  force_handlers: True

  roles:
  - role: consensys.peers_history
    vars:
      peers_history_version: 1.0.0

```

Run with ansible-playbook:
```
ansible-playbook -v /path/to/requirements.yml
```

### License

Apache


### Author Information

Consensys, 2025
