Parted
=========

Partition disks

Note : All disks will have the same partitionning. Separate in multiple subsequent parts if you want different partitionning for different disks

Requirements
------------


Role Variables
--------------

| Name | Type | Required | Default | Description
|--- |--- |--- |--- |---
| hdds | list | yes | None | List of the disks to partition
| partitions | list of dict | yes | [{'partition_type': 'primary', 'start_point': '0%', 'end_point': '100%'}] | Partitions to create on each disks
| create_label | boolean | no | true | Creates label on disks by default.
| label | string | no | gpt | Default label for disks

Dependencies
------------


Example Playbook
----------------

```
- hosts:
  - nc-9
  roles:
  - parted
  vars:
  - hdds:
    - /dev/sdb
  - partitions:
    - {'partition_type': 'primary', 'start_point': '0%', 'end_point': '10%'}
    - {'partition_type': 'primary', 'start_point': '10%', 'end_point': '50%'}
    - {'partition_type': 'extended', 'start_point': '50%', 'end_point': '100%'}


```

License
-------

GPLv3

Author Information
------------------

John Preston [John Mille]
