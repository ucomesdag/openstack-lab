
# openstack-lab
OpenStack test lab setup.

## Description
This will create a VM with, besides the vagrant user, the following users:

User            | Password
----------------|--------
student (wheel) | password
root            | redhat

#### server.example.com
* OpenStack dashboard: http://192.168.121.150 with user: admin and password: password
* Nagios: http://192.168.121.150/nagios with user: nagiosadmin and password: password

## Requirements
* Vagrant
* libvirt or VirtualBox
* atleast 4 GiB free memory (with recommended settings)
* atleast 20 GiB free storage  (with recommended settings)

## Install

```
cd openstack-lab
vagrant up
```

---