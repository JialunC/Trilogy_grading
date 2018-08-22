# TrilogyEdu Web Dev Assignment Grading VM

This vagrant env is for Web Dev TAs at Trilogy to grade their assignments, without having to setup/modify your local MySQL, or worrying about potential sql threats(such as damaging your existing data). You can always destroy the VM and restart it, while keeping your computer intact.

**Disclaimer: This is not developed by Trilogy**

## Getting Started
1. Install [VirtualBox](https://www.virtualbox.org/wiki/Downloads)
2. Install [Vagrant (1.9.1)](https://releases.hashicorp.com/vagrant/1.9.1/)
3. Install [Ansible (1.9.4)](http://docs.ansible.com/ansible/intro_installation.html#getting-ansible)
4. Clone this repo
5. Open your terminal `vagrant up` (from the repo directory). If this is the first time, it will take a bit for ansible to setup your vagrant machine.
6. Create a `repo` directory from the repo directory. Clone your students' assignments there.
 
**Run `vagrant halt`(from the repo directory) to stop the VM.**
**Run `vagrant destroy`(from the repo directory) to remove the VM**


## DB Information
- MySQL Password: qwerasdf (with full priv to all hosts)
- MySQL Username: grader
- MySQL Port: 3306
- MySQL Host: localhost

**You can find these DB info in `./ansible/host`**

## Grading Week 10 Assignments
1. Open your terminal `vagrant up`(from the repo directory). 
2. Open your terminal `vagrant ssh` (from the repo directory) to login to the VM.
3. Move to your students' projects. Import .SQL files from your students - `mysql -u grader -p database_name < student_file.sql`
4. Edit mysql.createConnection params in your students' projects, using the DB info above.
5. After npm installations and then you can start testing your students' projects.

## Debt
1. MySQL root user is not working. If you need to log into mysql as root, use `sudo mysql -u root`.
2. And more...