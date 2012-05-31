---
title: Backup Gem and Rails 3
layout: default
published: true
---

This is a test post

Nullam vitae turpis nulla. Quisque gravida arcu id turpis suscipit ac elementum leo ultrices. Nullam commodo hendrerit suscipit. Aenean ac neque neque, sit amet egestas sem. Phasellus in massa non lorem sagittis ornare eu vitae nisl. Donec pellentesque ullamcorper nunc, at ultrices ligula pharetra et. Cras quis pulvinar dui. Nullam pretium erat tincidunt ligula congue mattis. Vestibulum ornare rhoncus dui vel tempus

{% highlight ruby %}

********************************************************************************
Backup::Model.new(:npp_sites_backup, 'Backup NPP Sites') do

  database_yml = File.expand_path('../config/database.yml',  __FILE__)
  RAILS_ENV    = 'production'

  require 'yaml'
  config = YAML.load_file(database_yml)

  ##
  # MySQL [Database]
  #
  database MySQL do |db|
    db.name               = config[RAILS_ENV]["database"]
    db.username           = config[RAILS_ENV]["username"]
    db.password           = config[RAILS_ENV]["password"]
    db.host               = config[RAILS_ENV]["host"]
    db.port               = config[RAILS_ENV]["port"]
    db.socket             = config[RAILS_ENV]["socket"]
#   db.skip_tables        = ['skip', 'these', 'tables']
#   db.only_tables        = ['only', 'these' 'tables']
    db.additional_options = ['--quick', '--single-transaction']
  end

end

{% endhighlight %}
