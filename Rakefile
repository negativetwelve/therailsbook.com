# coding: utf-8

deploy_dir = "_deploy"
deploy_branch = "gh-pages"
config_files = Dir.glob("_config/*.yml").join(",")

ROOT = File.expand_path('.')

require 'rubygems'
begin
  require 'colored'
rescue LoadError
  raise 'You must "gem install colored" to use terminal colors'
end


desc "generate site"
task :generate do
  puts("Generating static site into _deploy")
  puts config_files
  system("jekyll build --config #{config_files}")
end

desc "deploy site"
task :deploy do
  puts "Getting ready to deploy."
  (Dir["#{deploy_dir}/*"]).each { |f| rm_rf(f) }
  puts "Generating site from source."
  Rake::Task[:generate].execute
  cd "#{deploy_dir}" do
    system("git add . --all")
    system("git add -u")
    puts "\n## Commiting: Site updated at #{Time.now.utc}"
    message = "Site updated at #{Time.now.utc}"
    system "git commit -m \"#{message}\""
    puts "\n## Pushing generated #{deploy_dir} website"
    system "git push origin HEAD:#{deploy_branch} --force"
    puts "\n## Github Pages deploy complete"
  end
end

desc "Starts the server to serve files locally"
task :jekyll do
  puts "Starting jekyll server."
  puts "Config files:"
  puts config_files
  sys("jekyll server --config #{config_files} --watch --port 4002")
end

def sys(cmd)
  puts ("> "+cmd).blue
  system(cmd)
end

task default: :jekyll
