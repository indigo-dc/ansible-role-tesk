EBI-TESK ansible role
=====================

This role install EBI-TESK: https://github.com/EMBL-EBI-TSI/TESK

Requirements
------------

A working Kubernetes cluster version 1.8 and later.

Role Variables
--------------

### defaults file for ansible-role-tesk ###

``tesk_FS_path``: path to install TESK (default ``/``)

``tesk_path``: TESK directory (default: ``/TESK``)

``tesk_deployment_path``: tesk deployment recipes path (default: ``/TESK/deployment/common``)

``tesk_sevice_type``: expose tesk service directly or not ( default: ``NodePort``)

``tesk_port``: tesk port (default ``'30080``)

``tesk_version``: tesk version to clone (default: ``master``)

``auth_mode``: enable AAI (default: ``'noauth``)

### Currentrly ftp configuration is mandatory! ###
It has to be enabled and configured!

``mount_ftp``: mount ftp server (default: ``false``)

``taskmaster_ftp_secret_name``: ftp secret name (default: ``ftp-secret``)

``teskmaster_ftp_url``: ftp server url (default ``ftp://ftp-private.ebi.ac.uk``)

``teskmaster_ftp_user``: ftp server username (default: ``user``)

``teskmaster_ftp_password``: ftp server user password (default: ``password``)

### Kubernetes customisation ###
Autoprovisioning is mandatory.
Currently supported: NFS (default). Cinder will be soon added, too.

``provisioner``: set autoprovisioner (default: ``nfs``)

### NFS provisioner configuration ###
``nfs_provisioner``:

 * ``path``: nfs mountpoint (default: ``/export``)
 *``export``: exports configuration (default: ``*(rw,async,no_root_squash,no_subtree_check)``)

Example Playbook
----------------

Install and configure TESK:

    - hosts: servers
      roles:
         - { role: indigo-dc.tesk, x: 42 }

License
-------

Apache 2

Author Information
------------------

Marco Antonio Tangaro (ma.tangaro@ibiom.cnr.it)
