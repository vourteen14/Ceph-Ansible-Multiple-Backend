Create Python Virtual Envirotment
- `````sudo apt install python3-venv -y`````
- `````python3 -m venv ceph`````
- `````source ceph/bin/activate`````
- `````pip install -U pip`````

Clone Ceph Repository
- `````git clone https://github.com/ceph/ceph-ansible.git`````
- `````cd ceph-ansible`````
- `````git checkout stable-5.0`````
- `````pip install -r requirements.txt`````

Copy Requirement Files
- `````cp site.yml.sample site.yml`````
- `````cp group_vars/all.yml.sample group_vars/all.yml`````
- `````cp mons.yml.sample group_vars/mons.yml`````
- `````cp osds.yml.sample group_vars/osds.yml`````
- `````cp group_vars/mgrs.yml.sample group_vars/mgrs.yml`````
- `````cp group_vars/mdss.yml.sample group_vars/mdss.yml`````

Edit file group_vars/all.yml
- Adjust as below
  - `````---`````
  - `````dummy:`````
  - `````ceph_origin: repository`````
  - `````ceph_repository: community`````
  - `````ceph_stable_release: pacific`````
  - `````monitor_interface: ens160`````
  - `````monitor_address: [MONITOR_CEPH_ADDR]`````
  - `````monitor_address_block: [CEPH_NETWORK]`````
  - `````public_network: [CEPH_NETWORK]`````
  - `````osd_objectstore: bluestore`````
  - `````mds_max_mds: 10`````
  - `````dashboard_enabled: True`````
  - `````dashboard_protocol: https`````
  - `````dashboard_port: 8443`````
  - `````dashboard_admin_user: admin`````
  - `````dashboard_admin_password: [CEPH_ADMIN_PASSWORD]`````
  - `````dashboard_frontend_vip: [DASHBOARD_CEPH_ADDR]`````
  - `````grafana_admin_password:[CEPH_GRAFANA_PASSWORD]`````

Edit file group_vars/osds.yml
- Adjust as below
  - `````---`````
  - `````dummy:`````
  - `````devices:`````
  - `````  - /dev/sdb`````
  - `````  - /dev/sdc`````
  - `````osd_auto_discovery: false`````
  - `````lvm_volumes:`````
  - `````- data: hdd-data-lv`````
  - `````  data_vg: hdd-data-vg`````
  - `````  journal_lv: hdd-journal-lv`````
  - `````  crush_device_class: hdd`````
  - `````- data: ssd-data-lv`````
    `````  data_vg: ssd-data-vg`````
    `````  journal_lv: ssd-journal-lv`````
    `````  crush_device_class: ssd`````
