## Directions
*  Ensure that Ansible v1.9.4 or greater is deployed on the node.
   *  `sudo add-apt-repository -y ppa:ansible/ansible-1.9`
   *  `sudo apt-get -y update`
   *  `sudo apt-get -y install ansible`
   *  Verify version with `ansible --version`.
*  Set an appropriate file in `/etc/ansible/hosts`.  For this you can copy `ansible-hosts` from this repository to `/etc/ansible/hosts` to run all of the ansible roles in this repo on the node (you will have to run this next step before doing this, though).
*  Clone this repo to the node you want to bootstrap.
*  `cd` into the `pm-ansible` folder.
*  Run `ansible-playbook playbook.yml`.

## Roles Included
### Common
Common tasks.  Uses apt-get to upgrade all installed software and install python and git.

### Web
Installs nginx and sets a basic index.html page to inform that the playbook has run.

### DB
Installs PostgreSQL and creates a test database.

### Monitoring
Runs on `all` nodes.  Installs the netdata monitoring framework (exposed on TCP:19999)