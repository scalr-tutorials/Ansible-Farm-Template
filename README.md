# Ansible-Farm-Template

## Create a Scalr Farm via Ansible and Scalr-CTL (Infra as Code)

### Setup instructions

The instructions below are written for Ubuntu 16.04. Adapt as necessary for other distributions.

#### Ansible/Scalr setup

- Install the required packages:
```
apt-get install ansible python-pip
pip install scalr-ctl
```

#### Pre Requisites
- Scalr API keys: https://api-explorer.scalr.com/
- Scalr farm template: https://scalr-wiki.atlassian.net/wiki/spaces/docs/pages/91036762/Farm+Templates

#### Instructions
- Main.yml is the playbook that will be executed, main.yml will call git_clone.yml, create_farm.yml, and remove_local_repo.yml
- You must update the vars.yml file with your variables
- The output of the scalr-ctl commands should be in JSON, ensure your config file has json set as the output style. Example:
```
API_HOST: my.scalr.com
API_KEY_ID: API_Key_ID
API_SCHEME: https
API_SECRET_KEY: API_Secret_Key
SSL_VERIFY_PEER: true
accountId: '1'
colored_output: true
envId: '1'
view: json
```
- Run the playbook:
```
ansible-playbook main.yml
```
