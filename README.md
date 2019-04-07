# Local Mediawiki

Quickly set up a Mediawiki wiki in your local environment. It will install the new site in a directory `installed/web` under the project's root directory.


## Installation

1. Clone this repo.

    ```
    git clone https://github.com/klenwell/local-mediawiki.git
    cd local-mediawiki
    ```

2. Review and adjust settings in `devops/ansible/var/main.yml`.

3. Run playbook.

    ```
    cd devops/ansible
    ansible-playbook playbook.yml --ask-become-pass -v
    ```

4. Site should be accessilbe. Default:

    - https://wiki.klenwell.localhost/

### Wipe Installation

To wipe the installation so that you can test the playbook from scratch, run these commands from local-mediawiki root directory:

```
sudo rm -Rf installed
mysql -u<DB_USER> -p -e "DROP DATABASE <DB_NAME>;"
```
