# BATMACHINE-Dataspace
Open-source resources and configuration examples for the BATMACHINE dataspace.

## Overview

This repository supplements the BATMACHINE dataspace paper by providing selected resources that can help developers reproduce the described setup using open-source components.

It does not provide a complete installation or the Ansible role implementations. Developers are expected to install and configure the listed components for their own environment.

## Included Resources

The repository includes:

- An Ansible playbook listing the required components in `playbook.yml`
- A Telegraf node list or configuration example
- A TimescaleDB initialization script
- Ontologies 
- Example of Kadi4Mat slurry recipe card at `Kadi4Mat/slurry_batmachine_demo.json`

## Components

The setup uses the following components:

### Data collection and storage

- Docker
- MinIO
- OPC UA PLC server
- TimescaleDB
- Mosquitto
- Telegraf
- MQTT-to-TimescaleDB service

### Application services

- Apache Jena Fuseki
- MongoDB
- OPC UA control service
- Grafana
- FastFuseki
- Frontend

### Kadi4Mat

- PostgreSQL
- Redis
- Elasticsearch
- Kadi4Mat
- Celery
- Celery Beat
- Apache HTTP Server

Latest version  of Kadi4Mat can be found at https://gitlab.com/iam-cms/kadi-docker
To set up default users: Go to KADI CLI (do a docker exec into kadi docker container), and run kadi db sample-data --force --i-am-sure , and the list of users can be found here: https://kadi4mat.readthedocs.io/en/stable/installation/development/installation.html

The dataspace backend can be found at : https://github.com/HEU-BATMACHINE/Dataspace_backend

## Ansible Playbook

Found at `playbook.yml`

The playbook defines the required component roles. The role implementations are not included and must be created or adapted by the developer.

## Reproduction

1. Install Ansible, Docker, and any other prerequisites required by the selected component versions.
2. Create the Ansible roles listed in the playbook.
3. Configure service addresses, ports, credentials, storage locations, and component versions for the target environment.
4. Use the supplied Telegraf configuration to connect to the OPC UA server.
5. Apply the supplied initialization script to TimescaleDB.
6. Load the supplied ontologies and mappings into Fuseki.
7. Import or recreate the supplied slurry recipe card in Kadi4Mat.
8. Run the playbook and verify the workflow described in the paper.

## Security and Data Handling

Security, access control, and data management are deployment-specific and are the responsibility of the user. Consult the documentation of each component for applicable guidance.
