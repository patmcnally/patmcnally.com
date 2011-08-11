---
title: Backup Gem and Rails 3
layout: default
published: true
---

This is a test post

{% highlight ruby %}

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

  ##
  # Amazon Simple Storage Service [Storage]
  #
  #  - ap-northeast-1
  #  - ap-southeast-1
  #  - eu-west-1
  #  - us-east-1
  #  - us-west-1
  #
  store_with S3 do |s3|
    s3.access_key_id      = 'access_key_id'
    s3.secret_access_key  = 'somethign_secret'
    s3.region             = 'us-east-1'
    s3.bucket             = 'npp-sites'
    s3.path               = "/database/#{config[RAILS_ENV]["database"]}"
    s3.keep               = 20
  end



  ##
  # Amazon Simple Storage Service [Syncer]
  #
  sync_with S3 do |s3|
    s3.access_key_id     = 'access_key_id'
    s3.secret_access_key = 'something_secret'
    s3.bucket            = "npp-sites"
    s3.path              = "/assets"
    s3.mirror            = true

    s3.directories do |directory|
      directory.add "/srv/npp-sites/shared/system"
      directory.add "/srv/npp-sites/shared/videos"
    end
  end

  ##
  # Gzip [Compressor]
  #
  compress_with Gzip do |compression|
    compression.best = true
    compression.fast = false
  end

  ##
  # Mail [Notifier]
  #
  notify_by Mail do |mail|
    mail.on_success           = true
    mail.on_failure           = true

    mail.from                 = 'sender@gmail.com'
    mail.to                   = 'destination@example.com'
    mail.address              = 'smtp.gmail.com'
    mail.port                 = 587
    mail.domain               = 'gmail.com'
    mail.user_name            = 'example@gmail.com'
    mail.password             = 'passwer'
    mail.authentication       = 'plain'
    mail.enable_starttls_auto = true
  end

end

{% endhighlight %}