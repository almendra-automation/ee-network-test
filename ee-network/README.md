# ee-network

Execution Environment for Network Automation

## What's included

### Ansible collections

| Collection | Version | Source |
|---|---|---|
| cisco.ios | - | Private Automation Hub (rh-certified) |
| cisco.nxos | - | Private Automation Hub (rh-certified) |
| cisco.iosxr | - | Private Automation Hub (rh-certified) |
| arista.eos | - | Private Automation Hub (rh-certified) |
| community.general | - | Private Automation Hub (community) |
| ansible.netcommon | - | Private Automation Hub (rh-certified) |
| ansible.posix | - | Private Automation Hub (rh-certified) |
| asalgado.ansible_content_collection_example2 | - | Github (github-public) |

### Python packages

- `requests`

### System packages

- `libssh-devel [platform:rpm]`

## Details

- **Tags:** `execution-environment`

- **Image registry:** `aap-aap-deploy.apps.rosa.rosa-pcnmk.cwjh.p3.openshiftapps.com/ee-network:latest`

## Use this execution environment

If your EE uses collections from private sources (Automation Hub, private automation hub), update the token settings in `ansible.cfg` before building.


Log in to the registry and pull the image:

```bash
podman login aap-aap-deploy.apps.rosa.rosa-pcnmk.cwjh.p3.openshiftapps.com
podman pull aap-aap-deploy.apps.rosa.rosa-pcnmk.cwjh.p3.openshiftapps.com/ee-network:latest
```

If the registry uses a self-signed certificate, you may need to append `--tls-verify=false` to each `podman` command.

To use it in Ansible Automation Platform:

1. Go to **Automation Execution** > **Infrastructure** > **Execution Environments**.
2. Click **Create execution environment** and enter the image URL: `aap-aap-deploy.apps.rosa.rosa-pcnmk.cwjh.p3.openshiftapps.com/ee-network:latest`
3. Select this execution environment in your job templates.

## Build details

- **Base image:** `registry.redhat.io/ansible-automation-platform/ee-minimal-rhel8:2.18`
- **Definition file:** `ee-network.yml`
- **Template file:** `ee-network-template.yml` - import this into Ansible automation portal to let others create EEs from the same starting point.

To make changes, use this EE's template in Ansible automation portal or rebuild manually with `ansible-builder` and the definition file.
