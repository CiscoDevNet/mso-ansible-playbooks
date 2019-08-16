<<<<<<< HEAD
# Ansible Cisco ACI Multi-Site Orchestrator Playbooks

The Cisco ACI Multi-Site Orchestrator (MSO) is responsible for provisioning, health monitoring, and managing the full lifecycle of Cisco ACI networking policies and stretched tenant policies across Cisco ACI sites around the world. It essentially represents the single source of truth for these policies.

These Ansible playbooks and supporting files enable the configuration and deployment of ACI Policy in the Data Center and Cloud.

## Resources

Learing Labs:
[Introduction to Ansible](https://developer.cisco.com/learning/modules/sdx-ansible-intro)


## Prerequisites:

- MSO version 2.1
- Minimally two ACI fabrics provisioned on the MSO as sites with fully operational multi-site configuration and vCenter/ESXi hosted VMs.

## Dependancies

- Ansible 2.8.x
- Python 3.7.x

## Configuration / Getting Started

- Review the `vars` and `hosts` files and update to reflect your data center.

- Start with the [master.yml](master.yml) playbook.

- Explore the playbooks referenced within and the [data model](vars/customer_01.yml).

## Caveats:

- For validation of workflow and logic a setup with 2 ACI fabrics, vCenter, and MSO 2.1 with working multi-site setup is required.

- The data model is fairly flat due to how the modules are set up and the need to keep playbooks linear.

    + There is a tradeoff, as the model could be more hierarchical in structure which would drive more complexity into the playbooks (i.e. requiring roles and more complicated looping or JSON queries)

- Module design feedback: a big challenge lies in that certain object relationships can be one-to-many but most modules only allow one-to-one in a single operation.
