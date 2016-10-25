# Role Name

[![Build Status](https://travis-ci.org/chouseknecht/filebeat-container.svg?branch=master)](https://travis-ci.org/chouseknecht/filebeat-container)

Adds a filebeat service to your [Ansible Container](https://github.com/ansible/ansible-container) project. Run the following commands
to install the service:

```
# Set the working directory to your Ansible Container project root
$ cd myproject

# Install the service
$ ansible-container install chouseknecht.filebeat
```

## Requirements

- [Ansible Container](https://github.com/ansible/ansible-container)
- An existing Ansible Container project. To create a project, simply run the following:
    ```
    # Create an empty project directory
    $ mkdir myproject

    # Set the working directory to the new directory
    $ cd myproject

    # Initialize the project
    $ ansible-contiainer init
    ```

## Role Variables

```
filebeat_elasticsearch_hosts: []
filebeat_logstash_hosts:
  - logstash:5044
```
> Define the filebeat logstash and elasticsearch output hosts. Each requires a list, where `[]` represents an empty list. When using the default configuration file, the container 
will fail unless you provide at least one logstash host or one elasticsearch host. The host does not actually have to exist or be reachable, it just has to be named in the config
file. 

## Dependencies

Although not strictly required, a container created from this role is fairly useless without an associated logstash or elsasticsearch service. Pair this service with one or both 
of the following: 

- [chouseknecht.elasticsearch-container](https://galaxy.ansible.com/chouseknecht/elasticsearch-container)
- [chouseknecht.logstash-container](https://galaxy.ansible.com/chouseknecht/logstash-container) 

## License

Apache v2

## Author Information

[@chouseknecht](https://github.com/chouseknecht)


