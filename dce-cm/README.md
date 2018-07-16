# dce-cm
Configuration Management for DCE Infrastructure


# Prerequisites 
 Ansible 2.5.4 installed
 boto, boto3, botocore for any repo dealing with AWS

## How to use this repository
### Install the right ssh key
We use a shared ssh key called `dceserverbuilds.pem` for initial connection to DCE
AWS systems. Ask Mark or Bess if you need a copy.
### Clone the repo and its submodules
```
  git clone --recurse git@github.com:curationexperts/dce-cm
  cd dce-cm
```

## To build a standard hosting server
Add the hostname to the `hosts` file under hosting clients. Then:
```
ansible-playbook build_dce_ldap.yml --ask-vault-pass --extra-vars "host=YOUR_HOSTNAME"

```

## To build an LDAP / shibboleth server
```
  ansible-playbook build_dce_ldap.yml --ask-vault-pass
```
This will prompt you for our ansible vault password. It is kept in LastPass.
Ask Mark or Bess if you need access to it. It is required to decrypt our SSL
certs

## Splunk
To add additional log paths, edit vars/main.yml, to change the defaults edit defaults/main.yml
To delete splunk run the role with the delete-splunk tag
