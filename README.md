uclalib_role_rkebootstrap_targeted
=========

This role is meant to be run against a UCLA Library provisioned Rancher RKE cluster to bootstrap initial components.

Cluster components this roles installs/configures:
  * cert-manager operator
  * external-secrets operator
  * MetalLB operator
  * Ingress NGINX Controller
  * calico container network interface configurations and global policies customizations
  * vsphere cloud provider interface and container storage interface plug-ins 

Requirements
------------

You must have a Rancher RKE cluster provisioned using the UCLA Library's templates in vSphere.

Role Variables
--------------

### Variables you must define (that do not have defaults):

To connect to the Rancher Manager, you must have the following variables defined:

  * `rancher_token`
  * `rancher_api_url`

To identify the target RKE cluster and load balancer IP, you must specify:

* `rke_cluster_id`
* `loadbalancer_ip`

To connect to the vCenter environment, you must have the following variables defined:

  * `vcenter_fqdn`
  * `vcenter_insecure_flag`
  * `vcenter_datacenter_name`
  * `vcenter_username`
  * `vcenter_user_password`
  * `vcenter_port`
  * `vcenter_datastore_url`

Specifiy package versions:

  * `kubectl_version`
  * `helm_version`
  * `cert_manager_version`
  * `external_secrets_version`
  * `rke_bootstrap_version`

Specifiy external secret AWS access credentials for each secret domain:

  * `es_services_access_key`
  * `es_services_secret_access_key`
  * `es_systems_access_key`
  * `es_systems_secret_access_key`

Specify access information to our Sectigo ACME provider:

  * `sectigo_acme_tls_key`

