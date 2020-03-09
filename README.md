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
Once the playbook finishes, it will generate the report in a HTML file OpenShift_Cluster_Overview_Report_<date>.html

The playbook can email the report to one or more recipents as well.
Set the `email_report:` to True and provide the SMTP configuration in cluster-report.yaml

```yaml
    email_report: True
    email_from: khizernaeem@gmail.com (OpenShift Cluster Overview)
    email_recipients:
      - khizernaeem@gmail.com
      - knaeem@redhat.com
    smtp_host: smtp.gmail.com
    smtp_port: 587
    smtp_user: khizernaeem@gmail.com
    smtp_pass: xxxxxx

```

# Sample

# Contribution
