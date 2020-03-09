# Open Shift Cluster Report
---

This playbook generates a cluster overview report for an **Open Shift 3** Cluster.

# Features

# Usage

Simply Clone this repository on the ansible node of the cluster:

```bash
git clone https://github.com/kxr/ocpcr.git
```

Change into the directory:

```bash
cd ocpcr
```
And run the cluster-report.yaml playbook

```
ansible-playbook cluster-report.yaml
```

If the ansible inventory of the cluster is in a non-default location, specify it with -i:

```bash
ansible-playbook cluster-report.yaml -i /root/ocp311-inventory
```

# Sample

# Contribution
