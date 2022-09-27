Ansible role: Cassandra
=======================

Install and configure Apache Cassandra.

Role Variables
--------------

```
ENTRY POINT: main - Install and configure Apache Cassandra

OPTIONS (= is mandatory):

- cassandra_apt_key_fingerprints
        Fingerprints for cassandra apt keys
        [Default: (null)]
        elements: str
        type: list

- cassandra_cluster_name
        Name of the cluster
        [Default: Test Cluster]
        type: str

- cassandra_listen_address
        Bind address
        [Default: localhost]
        type: str

- cassandra_rpc_address
        Listen address for RPC client connections
        [Default: localhost]
        type: str

- cassandra_rpc_port
        Listen port for RPC client connections
        [Default: 9160]
        type: int

- cassandra_series_version
        Cassandra version series to track, for available versions see: https://cassandra.apache.org/doc/latest/cassandra/getting_started/installing.html#installing-the-debian-packages
        [Default: 311x]
        type: str
```

Installation
------------

This role can either be installed manually with the ansible-galaxy CLI tool:

    ansible-galaxy install git+https://github.com/wandansible/cassandra,main,wandansible.cassandra
     
Or, by adding the following to `requirements.yml`:

    - name: wandansible.cassandra
      src: https://github.com/wandansible/cassandra

Roles listed in `requirements.yml` can be installed with the following ansible-galaxy command:

    ansible-galaxy install -r requirements.yml

Example Playbook
----------------

    - hosts: cassandra_hosts
      roles:
         - role: wandansible.cassandra
           become: true
           vars:
             cassandra_cluster_name: "Primary Cluster"
