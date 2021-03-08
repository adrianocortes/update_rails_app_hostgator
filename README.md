# Update Rails App in Hostgator VPS with Ansible

This is a ansible playbook for update a rails app hosted in a HostGator VPS


## Requirements

- python
- pip
- ansible

<br>
<br>
## Instalation
<br>
<br>

### CentOS

```bash
sudo yum install -y python pip
sudo yum install -y ansible
```
<br>
<br>

### Ubuntu

```bash
sudo apt install -y python pip
sudo apt install -y ansible
```
<br>
<br>

### MacOS
Python it's native in macOS

```bash
brew install ansible
```
<br>
<br>

## Setup


- Setup key ssh access for git repository
- Setup passwordless ssh access for a hostgator vps
- Setup rails app in Hostgator panel
<br>
<br>

## Parameters


Rename or copy file "hosts.sample" to "hosts"
In "hosts" file, update all parameters:


- hostname or ip => Hostgator IP or name for ssh access
- ssh_user => User for ssh access in hostgator VPS
- username => Project owner username ( same used for login in hostgator panel)
- repo_project => Complete git repo URL ( with protocol access "git" or "https")
- dir_project => Folder for rails app like defined in hostgator panel
- repo_key_file => SSH key file name for access git repository. Full path if out project folder. Just name if in files folder (project/files/)
- repo_branch => branch for git checkout. If not defined, default it's "main"
- ruby_version => Ruby version used in Hostgator app environment Ex.: ea-ruby27 
- rails_env => environment to be passed for rails commands
<br>
<br>

## Usage

In project folder, run command:

```bash
ansible-playbook -i hosts update_hostgator_rails_app.yml
```

<br>
<br>

## Contributing
Pull requests are welcome. For major changes, please open an issue first to discuss what you would like to change.

Please make sure to update tests as appropriate.
<br>
<br>

## License
[MIT](https://choosealicense.com/licenses/mit/)
