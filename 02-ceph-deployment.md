Create Python Virtual Envirotment
- `````sudo apt install python3-venv -y`````
- `````python3 -m venv ceph`````
- `````source ceph/bin/activate`````
- `````pip install -U pip`````

Clone Ceph Repository
- `````git clone https://github.com/ceph/ceph-ansible.git`````
- `````cd ceph-ansible`````
- `````git checkout stable-6.0`````
- `````pip install -r requirements.txt`````

Copy Requirement Files
- `````cp site.yml.sample site.yml`````
- `````cd group_vars/`````
- `````cp all.yml.sample all.yml`````
- `````cp mons.yml.sample mons.yml`````
- `````cp osds.yml.sample osds.yml`````
- `````cp mgrs.yml.sample mgrs.yml`````
- `````cp mgrs.yml.sample mgrs.yml`````
- `````cp mdss.yml.sample mdss.yml`````

Edit file /etc/neutron/neutron.conf
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
  - `````dashboard_frontend_vip: [DASHBOARD_CEPH_ADDR]''`````
  - `````grafana_admin_password:[CEPH_GRAFANA_PASSWORD]`````
