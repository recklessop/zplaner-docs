# Getting Started with `zplanner`

## Getting Started

This is the zPlanner Quick Start page. Here you will find a minimal amount of information on how to get zPlanner running.

`zPlanner` uses VMware PowerCLI to gather information about your virtual machines from vCenter. All of the PowerCLI cmdlets used by zPlanner require read-only access to vCenter and all virtual machines under that vCenter (including those in folders, resource groups, etc).

## zPlanner Requirements

zPlanner will require several things in order to do its job. A place to run, and credentials to talk to vCenter, as well as an IP address are the basics.

- At least 2 vCPU and 2GB of ram, for more than 500vms use 4vCPU and 4GB of RAM
- IP address (Static or DHCP), main requirement is that it has to be able to talk to vCenter
- vCenter username and password (can be a read only account), preferably in user@domain format

## Downloading the zPlanner Appliance

As stated before, zPlanner is deployed via a virtual appliance. The OVA file that you can download will run on ESXi 4.0 or newer, it has not been tested on non-esxi platforms.

To download the zPlanner Virtual Appliance go to https://www.jpaul.me/getzplanner

## Deploying zPlanner

To deploy zPlanner after you have downloaded the OVA file, login to vCenter or ESXi, and follow the standard OVF/OVA Template deployment procedures for the version you are running. (This is a VMware procedure, if you need more details please refer to VMware documentation on how to deploy an OVA template.)

## Configuration of zPlanner

Once the virtual appliance has been deployed configuration is very straightforward. There is a console based menu available via the virtual machine console or via an SSH terminal. It is recommended that for initial configuration you use the virtual machine console.

### Setup networking

Open the VM console and wait for the VM to fully boot. Once you see the VM console check to see if the machine received an IP address via DHCP. If it has not, run the static network configuration wizard by typing "2" and pressing enter.

### Updating zPlanner

Once the VM has a valid IP address, make a note of it, then run the update wizard by pressing "1" then enter. This procedure will download the latest zPlanner code from the zPlanner repo, apply the latest Grafana Dashboards, and then reboot the appliance.

### Configure vCenter information

Once the appliance has rebooted continue the configuration process by pressing "3" followed by enter. In this step we will configure the vCenter credentials. Enter the following information:
- vCenter FQDN or IP
- vCenter username either user@domain or domain\\user (note the double \\)
- vCenter user's password

### Test vCenter information

Next, at the main menu press option "4" followed by enter. a PowerCLI script will run and test the vCenter information that you entered. There will be error messages displayed if there are issues with the connection information. If you see any error messages re-run option 3 at the main menu to re-enter your connection information.

Once there are no error messages return to the main menu and proceed to the next section

### Generate the list of virtual machines

Before we can select which VMs to monitor in the GUI we need to get the list of VMs from vCenter. To do this type "5" at the main menu and press enter. This step can take a little time depending on how many virtual machines you have in your vCenter inventory.

Once it is complete return to the main menu.

### Start the Job Scheduler

zPlanner uses cron to schedule PowerShell jobs. By default no jobs are running and no stats will be collected until you start the job scheduler. Simply running option "6" will install the required Cronjobs.

If for whatever reason you need to stop the scheduled jobs, run option "7" and all of the cronjobs will be removed.

### Selecting vms to Monitor

From this point forward we can proceed to the Web UI of zPlanner. simply go to http://zPlanner_IP_Address_in a web browser

From here we will need to select the VMs to monitor. In the main menu ribbon select "Monitor VMs" and then pick "Add VMs"

From the web page select which VMs you wish to monitor and click the "Monitor" button, you can repeat this step as many times as needed.