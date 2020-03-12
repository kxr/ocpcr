# Open Shift Cluster Report

This playbook generates a cluster overview report for an **Open Shift 3** Cluster.

---

# Features

* Requires no additional dependency
* Generates a stand-alone HTML file
* Light-weight and fast
* A total of 3 oc commands are run on the cluster, data is processed on the ansible node.
* Modular design, new report components can be easily added

If you would like to request a new component/features in the report, please open a new github issue.

# Usage

Clone/copy this repository on the ansible node of the cluster:

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
Once the playbook finishes, it will generate the report in a HTML file OpenShift_Cluster_Overview_Report_\<date>.html

The playbook can email the report to one or more recipents as well.
Set the `email_report:` to True and provide the SMTP configuration in cluster-report.yaml

```yaml
    email_report: True
    email_from: cluster-report@email.com (OpenShift Cluster Overview)
    email_recipients:
      - khizer@email.com
      - someone@email.com
    smtp_host: smtp.gmail.com
    smtp_port: 587
    smtp_user: smtp_auth_user@email.com
    smtp_pass: xxxxxx

```

# Sample
![OpenShift Cluster Overview Report 2020-03-09](https://user-images.githubusercontent.com/10104541/76197494-ae7ce280-6205-11ea-8b26-cc1c8d0676c0.png)

# TODO

* Check for orphaned pods
* Compare the master-config.yaml
* Elasticsearch status
* Warning events in the core namespaces


# Contribution

This is work in progress and I will be adding more components to the report. To understand the architecture of the playbook / jinja templating, please see the wiki section.

Please feel free to write new components and send a pull request.
