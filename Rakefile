def jekyll(opts="", path="")
  sh "rm -rf _site"
  sh path + "jekyll " + opts
end

desc "Build site using Jekyll"
task :build do
  jekyll "--no-auto"
end

desc "Serve on Localhost with port 4000"
task :default do
  jekyll "--server --auto --pygments"
end

desc "Serve on Localhost with port 4000 using development version"
task :unstable do
  jekyll "--server --auto", "../jekyll/bin/"
end

desc "Deploy to Dev"
task :deploy => :"deploy:dev"

namespace :deploy do
  desc "Deploy to Dev"
  task :dev => :build do
    rsync "dev.patmcnally.com"
  end

  desc "Deploy to Live"
  task :live => :build do
    rsync "patmcnally.com"
  end

  desc "Deploy to Dev and Live"
  task :all => [:dev, :live]

  def rsync(domain)
    sh "rsync -avz -e 'ssh -p 23700' _site/ pat@morphine.patmcnally.com:/srv/#{domain}/"
  end
end
