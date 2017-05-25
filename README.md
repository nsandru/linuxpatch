# Linux patching - update linux systems

Ansible playbooks for automated updates of RHEL and CentOS systems

Usage:
  ansible-playbook patchallnodes.yml -i <inventory_file> \
    -e hostcluster=<hostcluster> \
    -e service=<service_to_stop_and_start> \
    [ -e timeout=<service_start_stop_timeout> ] \
    [ -e hostsparallel=<number_of_hosts_to_run_in_parallel> ] \
    [ -e yumtimeout=<yum_update_timeout> ] \
    [ -e dryrun=true ]
    
  hostcluster = (Mandatory) The name of the host or hostcluster to be updated. It has to be listed in the inventory.
  service_to_stop_and_start = (Mandatory) The name of the service to be stopped before update and started aftewards.
  service_start_stop_timeout = (Default 300) Time to wait (seconds) for the service to stop and start.
  number_of_hosts_to_run_in_parallel = (Default 5) Number of hosts to be updated at the same time. Set to 1 for rolling updates.
  yum_update_timeout = (Default 1200) Time to wait (seconds) for the yum update.
  dryrun=true - Check the configurations without updating anything
 
