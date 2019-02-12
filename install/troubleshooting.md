# Troubleshooting zPlanner Install Issues

## Common Installation issues

### Long boot time on first boot

![no dhcp](images/dhcp-missing.png)
If you are experiencing a long boot time after deploying the OVA, chances are that DHCP is not present on the virtual network where you attached the appliance. It will take approximately 5 minutes for Ubuntu to "give up" on DHCP and move on.
Once the appliance has booted up and you are at the console menu, select option 2 to configure a static IP address. Once you have configured a static IP address the appliance will boot up much quicker.

### Unable to connect to vCenter

![no dhcp](images/vcenter-invalid-hostname.png)
If you are experiencing a

### Invalid vCenter Credentials

![no dhcp](images/vcenter-creds.png)
If you are experiencing a

### Only a partial VM list is available in Web UI

![no dhcp](images/vm-list-partial.png)
If you are experiencing a