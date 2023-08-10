# Jetson ML Setup Guide

NVIDIA's Jetson line of products are powerful embedded computers. This guide walks through the setup of a Jetson AGX Orin Developer Kit, from initial flashing
through software setup and testing.

---

## Contents

*Hardware*:

- Jetson AGX Orin 64GB module
- Samsung 970 EVO Plus 1TB NVMe drive

**Software**

- Ansible
- NVIDIA JetPack 5.1.1+


## Steps

1. Update `inventory/jetson.yml` with the username and host address for your Jetson
2. Run the playbook. Be sure to pass in the sudo password so ansible can run commands as root for e.g. `apt-get`. This step will take several minutes as it involves installing
   the NVIDIA JetPack components.

```
$ ansible-playbook 01-setup.yml -i inventory --ask-become-pass
BECOME password: 

PLAY [Initial setup of device] **************************************************************************************************************************************************************

TASK [Gathering Facts] **********************************************************************************************************************************************************************
ok: [agx-orin-devkit]

TASK [Update system package cache] **********************************************************************************************************************************************************
changed: [agx-orin-devkit]

TASK [Install jetpack] **********************************************************************************************************************************************************************
```

