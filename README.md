# vagrant-nginx-php5.6-mysql

Install
-------

Edit the `ansible/group_vars/dev.local.yml` file to override the parameters in dev.yml.

Run:

```
git clone git@github.com:Nyxis/vagrant-nginx-php5.6-mysql.git vagrant
cd vagrant
vagrant up
```

Add this to your local /etc/hosts:

```
192.168.100.50 your.project.hostname
```

And you're good to go!


Usage
-----

`vagrant up`: Boot the VM.
`vagrant up --provision`: Boot the VM and provision it by runing the ansible playbook.
`vagrant halt`: Stop the VM.
`vagrant priovision`: Run the ansible playbook.
`vagrant destroy`: Delete the VM.


Adding a new project
--------------------

Edit the `ansible/group_vars/dev.yml` file and add the things you want (vhost, db, ...).
Edit your `/etc/hosts` to add the new domain and point it to the VM ip.

Then reprovision the VM by running:

```
vagrant provision
```


Troobleshooting
---------------

If `vagrant up` hangs with:

```
default: Warning: Remote connection disconnect. Retrying...
```

Change the value `Ubuntu` to `Ubuntu (64 bit)` under Settings/General via the VirtualBox GUI. This appears to be a miss-configuration of the box image.
