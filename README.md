# Local Mediawiki

Quickly set up a Mediawiki wiki in your local environment.


## Installation

1. Clone this repo.

    ```
    git clone https://github.com/klenwell/local-mediawiki.git
    ```

2. Run playbook.

    ```
    cd local-mediawiki/devops/ansible
    ansible-playbook playbook.yml --ask-become-pass -v
    ```

### Wipe Installation

To re-run installation, run these commands from local-mediawiki root directory:

```
sudo rm -Rf installed
mysql -u<DB_USER> -p -e "DROP DATABASE <DB_NAME>;"
```
