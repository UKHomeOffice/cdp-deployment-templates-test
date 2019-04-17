Deployment repo for Common Data Platform
========================================

This repository contains the deployment template files for the
Common Data Platform (CDP).

Services provided
-----------------

1. GraphDB (JanusGraph) (Work in progress!)
2. ElasticSearch (for dev purposes only)

Notable directories
-------------------
* [`conf-template/`](./conf-template/) contains configuration templates with environment variable placeholders for each of the major cdp components.
* [`conf-template/graphdb/common/`](./conf-template/graphdb/common/) contains the common files for all the different graphdb personas
* [`conf-template/graphdb/persona/schema-loader/`](./conf-template/graphdb/persona/schema-loader/) contains the configuration files needed by the 'schema-loader' graph persona.  This  persona will apply a new graph schema to the environment.

* [`k8s-template/`](./k8s-template/) contains the Kubernetes template files.

* [`manifest/`](./manifest/) contains the URL to the image of each of the components.
* [`vars`](./vars) contains the common variables file

Adding a new component
----------------------

To add a new component, the following changes are needed:

1. create a new .yaml file in k8s-template  directory.  Note that file name should match the name of the service.
2. optionally add one or more configuration file templates (if the application requires) under the conf-template directory.  These files may have placeholders that are replaced with environment variables listed under vars/common.cfg.
3. edit the `vars/common.cfg` to add any new placeholders
