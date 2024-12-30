# manipulate_vmware_host_disk_info
Filter transformations for the output of the vmware_host_disk_info module from community.vmware

Community.vmware is a great Ansible content collection, however some of it's returns require quite a bit of cleanup to be useful. My use case required me to examine a VMware host's physical disks and their capacity using the `vmware_host_disk_info` module as a prerequisite to creating a new datastore. I was able to clean up the vmware_host_disk_info module's returns by using Ansible filters and regular expressions to pull out the information I needed and the `ansible.builtin.template` to store my cleaned data nicely in a yaml file that can be looped over later by Ansible.

There is probably a more elegant way to go about this, but this was my best swag at making sense of the (somewhat convoluted) structure of the data returned by vmware_host_disk_info module.