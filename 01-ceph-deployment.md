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
