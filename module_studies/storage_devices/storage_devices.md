# Create Partitions 

The parted module - Uses the parted command line tool in order to configure a block device partition.

### Example
```yaml
- name: Show options for parted module
  parted:
    device: /dev/sdb|/dev/nvme1n1
    number: 1
    state: present|absent|info
    part_end: 1GiB|100%
    label: msdos|gpt
    flags: [ lvm ]
```
