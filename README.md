Wordpress custom version for o2sources
===

Requirements
---
This custom version have "small" requirements. Install them once and a kitten will be happy.

- First, install [VirtualBox](https://www.virtualbox.org/),
- Next, install [Vagrant](https://www.vagrantup.com/)
- And then, install [Ansible](http://docs.ansible.com/intro_installation.html).

If your host is a Windows-based system, follow this blogpost: 
[Running Vagrant with Ansible Provisioning on Windows](http://www.azavea.com/blogs/labs/2014/10/running-vagrant-with-ansible-provisioning-on-windows/)  
_Note:_ Babun is strongly recommended instead of Cygwin.

After that, we need some Vagrant plugins for your convenience. In your terminal, 
use these commands:

```
vagrant plugin install landrush (could fail on windows)  
vagrant plugin install vagrant-hostmanager
vagrant plugin install vagrant-hostsupdater
vagrant plugin install vagrant-vbguest
```

For Windows users:

```
vagrant plugin install vagrant-winnfsd
```

Installation
---

Installation is quite simple and fully automatised.

First, clone this repository, go to the project folder and remove your origin remote.

```
git remote rm origin
```

Now custom the `:name` var in `Vagrantfile` at line 10 with your project name.
Ok, now run `vagrant up`, wait and have fun!

Install wordpress theme or plugin
---

Installation for wordpress theme or plugin is fuckin' easy. First go to the 
[official packagist for wordpress](http://wpackagist.org/) and search your plugin
or your theme.

Don't worry, this website contains all public wordpress plugin and themes.

Edit your `composer.json`, add your new dependency from wppackagist and run 
`composer update` from your VirtualMachine (run `vagrant ssh`).

__TIP:__ After a `composer update`, create a single commit with your 
`composer.json` and your `composer.lock` for avoid conflicts.

Install non-wordpress dependency
---
If you want to install non-wordpress dependency, go to [packagist](https://packagist.org/)
and feel free to follow the fuckin documentation!