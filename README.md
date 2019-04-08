# Local Mediawiki

Quickly set up a Mediawiki wiki in your local environment. It will install the new site in a directory `installed/web` under the project's root directory.

It has only been fully tested on my Ubuntu workstation, which may have already included some required packages.


## Installation / Usage

1. Clone this repo.

    ```
    git clone https://github.com/klenwell/local-mediawiki.git
    ```

1. Install required Ansible packages

    ```
    cd local-mediawiki/devops/ansible
    ansible-galaxy install -r requirements.yml
    ```

1. Review and adjust settings in `devops/ansible/vars/main.yml`.

1. Run playbook.

    ```
    ansible-playbook playbook.yml --ask-become-pass -v
    ```

1. Site should be accessible at `https://{{ wiki_domain }}/`. Default:

    - https://wiki.klenwell.localhost/

### Wipe Installation

To wipe the installation so that you can test the playbook from scratch, run these commands from local-mediawiki root directory:

```
sudo rm -Rf installed
mysql -u<DB_USER> -p -e "DROP DATABASE <DB_NAME>;"
```
