Netbox - Inventory Management System
You can run pynetbox to operate netbox

GNS3 - Network Simulation System
You can run python network related libraries against network devices in GNS3

Workflow:
- Run netbox in docker
- Populate data in netbox
- setup GNS3 wiht multiple vendor devices
- develop scripts to operate them

Download GNS3 labs from www.gns3.com/marketplace/labs

## Milestones

1. Nebox Data Validation
- Ansible, Nornir, Nornir-netbox, Nornir-napalm, Nornir-utils, Napalm, Pynetbox
- Build Test env
    - Netbox running in docker
    - Install requirements
    - Run network OS in VMs
    - Vdesk DNS
- Projects
    - Update all device serial_number (`serial`) and code_version filed in netbox
    - Check all devices NTP time settings
    - Check all device authentication settings
    - Collect all device facts
2. Develop NetEng own library to operate all different vendor network devices

