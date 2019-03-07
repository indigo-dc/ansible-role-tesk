EBI-TESK ansible role
=====================

This role install EBI-TESK: https://github.com/EMBL-EBI-TSI/TESK

Requirements
------------

A working Kubernetes cluster version 1.8 and later.

Role Variables
--------------

---
# defaults file for ansible-role-tesk

``tesk_FS_path``: path to install TESK (default ``/``)

``tesk_path``: TESK directory (default: ``/TESK``)

``tesk_deployment_path``: tesk deployment recipes path (default: ``/TESK/deployment/common``)

``tesk_sevice_type``: expose tesk service directly or not ( default: ``NodePort``)

``tesk_port``: tesk port (default ``'30080``)

``tesk_version``: tesk version to clone (default: ``master``)

``auth_mode``: enable AAI (default: ``'noauth``)

# Currentrly ftp configuration is mandatory!
# It has to be enabled and configured!

``mount_ftp``: mount ftp server (default: ``false``)

``taskmaster_ftp_secret_name``: ftp secret name (default: ``ftp-secret``)

``teskmaster_ftp_url``: ftp server url (default ``ftp://ftp-private.ebi.ac.uk``)

``teskmaster_ftp_user``: ftp server username (default: ``user``)

``teskmaster_ftp_password``: ftp server user password (default: ``password``)

# Kubernetes customisation
# Autoprovisioning is mandatory.
# Currently supported: NFS (default)
# Cinder will be soon provided, too.

``provisioner``: set autoprovisioner (default: ``nfs``)

# NFS provisioner configuration
``nfs_provisioner``:

  #. ``path``: nfs mountpoint (default: ``/export``)
  #. ``export``: exports configuration (default: ``*(rw,async,no_root_squash,no_subtree_check)``)

Dependencies
------------

A list of other roles hosted on Galaxy should go here, plus any details in regards to parameters that may need to be set for other roles, or variables that are used from other roles.

Example Playbook
----------------

Including an example of how to use your role (for instance, with variables passed in as parameters) is always nice for users too:

    - hosts: servers
      roles:
         - { role: username.rolename, x: 42 }

License
-------

BSD

Author Information
------------------

An optional section for the role authors to include contact information, or a website (HTML is not allowed).
