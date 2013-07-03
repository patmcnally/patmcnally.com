
  People bitch about the future and how long it's taken to get here; some would
  even argue that it's still not here yet. I'm looking at you dude with the
  "Where's my flying car t-shirt." Well fuck your flying car, god forbid my
  fellow motorist all of a sudden operate in three dimensions. But I digress,
  my point is you live in the a wonderous age, and if you're still trying to
  get your mac to match your deployment environment with the likes of brew,
  rbeenv, Gemfiles, or Composer, you're living in the fucking stone age.

  That's fine, I just recently put down my large branch and my favorite cutting
  rock and have come to accept the gospel of two parts. 1) Virtualization and
  2) Configuration Management. Now that I've put by barbaric pagan ways behind
  me, I ask you join me on this journey of salvation. No longer must you bear
  the pains of development environments being a minor version different from
  production, a minor version which breaks half your functionality the day
  before a major milestone. You are a civilized man, you eat with a knife and
  fork, so do what everyone other upright ape should be doing. You do not make
  soup by digging a hole and throwing hot rocks in there, you use a pot and
  stove like everyone else.

  Use Vagrant to associate each project with a custom Virtual Machine, use Salt
  to configure these virtual machines to be near-identical to your production
  boxes. And if you are so blessed as to be resposible for your own production
  environment, use the production salt environment I describe as well. Come
  sit, stay awhile, and let me convince you that no matter Ruby or PHP, this is
  the way of the future.

  Goals of this howto:
    1) Highlevel Vagrant overview, quickly link away for more
    2) Highlevel SaltState overview, quickly link away for more
    3) For each [Laravel, Rails 4]
      a) new project
      b) Vagrantfile
      c) Minionless Salt
        - Vagrant Enviroment
        - Product Enviroment
        - Heroku (????)

 Vagrant Plugins
  - [salty-vagrant]: (https://github.com/saltstack/salty-vagrant)
  - [vagrant-cachier]:(https://github.com/fgrehm/vagrant-cachier)
  - [vagrant-hostmanager]:(https://github.com/smdahlen/vagrant-hostmanager)


 # Install Vagrant
  1) Their directions: http://docs.vagrantup.com/v2/installation/


Rails Project:

  `rails new project_name`

  `cd project_name`

  `vagrant init`

Laravel Project:

  `composer create-project laravel/laravel project_name`

  `cd project_name`
  `git init`
  `git add .`
  `git commit -m 'initial commit'`

  `vagrant init`
  `git add .`
  `git commit -m 'Vagrantfile added'`

  Add submodle for states
  `vagrant plugin install vagrant-salt`
  `git submodule add ../salt-states-webapps/ salt/roots/salt`
  `git commit -m 'submodule providing states added'`

  Modify Vagrantfile to use Salt

  ---> At this point I need to get a salt-states that will work

  Add vhost for apache


For a production machine: https://library.linode.com/securing-your-server

IPTABLE


