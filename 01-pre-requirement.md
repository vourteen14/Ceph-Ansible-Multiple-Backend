PRE-OS-SETUP

- A running operating system ubuntu
- Network has configured
- Minimum disk 16 G
- Minumum memory 2G
- Minimum processor 1 core
- Openstack version in Wallaby

Sistem Information Node 1

- Hostname: ceph01
- OS: Ubuntu 20.04
- Memory: 4G
- Processor: 1 core
- Harddisk 1: 16G
- Harddisk 2: 10G
- Harrdisk 3: 10G
- Network 1: 10.10.10.110 - ens160

Sistem Information Node 2
- Hostname: ceph02
- OS: Ubuntu 20.04
- Memory: 4G
- Processor: 1 core
- Harddisk 1: 16G
- Harddisk 2: 10G
- Harrdisk 3: 10G
- Network 1: 10.10.10.111 - ens160

Sistem Information Node 3
- Hostname: ceph03
- OS: Ubuntu 20.04
- Memory: 4G
- Processor: 1 core
- Harddisk 1: 16G
- Harddisk 2: 10G
- Harrdisk 3: 10G
- Network 1: 10.10.10.113 - ens160

SETUP Operating System
- Add user to sudoer without password ( in case username is anggasuriana )
  - `````sudo su >> enter password`````
  - `````echo "anggasuriana ALL=(ALL) NOPASSWD: ALL" > /etc/sudoers.d/angga`````
  - `````exit && sudo su````` ( if no ask password adding success )

- Update and Upgrade Dependency
- `````sudo apt update && sudo apt upgrade -y`````
