# Create Logical Volumes
The lvg module, creates, removes and resizes volume groups.

### Example of lvg module
```yaml
- name: show options for lvg module
  lvg:
    force: no|yes
    pesize: 8
    pvs: /dev/nvme1n1p1,/dev/nvme2n1p1
    vg: vg_name
    state: present|absent
```
```yaml
- name: show options for lvol module
  lvol:
    vg: vg_name
    lv: lv_name
    size: 512m|1g|100%FREE
    state: present|absent
    shrink: yes|no
    resizefs: no|yes
    force: no|yes
    opts: free form options passed to the lvcreate command
  lvcreate command
```
