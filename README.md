# rhel6-base-ami

Base AMI for RHEL 6.10.

Things Packer does:
  * Deploys a EC2 instance to AWS based on the chosen AMI Id/Filter
  * Creates the SSH connection to the EC2 instance
  * Provisions the EC2 Instance by running Ansible
  * Captures the EC2 Instance as an AMI when Ansible completes successfully

Things Ansible does:
 * Installs EPEL for EL6 from archive URL 
    * (https://archives.fedoraproject.org/pub/archive/epel/6/i386/Packages/e/epel-release-6-8.noarch.rpm)
 * Runs CIS hardening for RL6
 * Installs and configures standard ClamAV install, no file exclusions have been added.
 * Installs CloudWatch and adds the config file to the correct location
 * Installs and configures Nagios client plugins and scripts
 * Installs/Checks the following packages:
    * openssl
    * openssh-server

