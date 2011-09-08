#!/usr/bin/env ruby

require 'rubygems'
require 'bundler/setup'

require 'railsless-deploy'
require 'capistrano-cowboy'


default_run_options[:pty] = true

set :user, "ec2-user"
set :application, 'my-movies'
set :deploy_to, "/srv/#{application}"

server "app", :app

after "deploy", "deploy:symlink"
after "deploy", "deploy:smoke"

namespace :deploy do
  task :symlink do
    run "#{sudo} ln -sf #{current_path} #{current_path}/#{application}"
  end

  task :smoke do
    command = []
    command << "curl"
    command << %(--write-out "HTTP %{http_code}, %{time_total} second response time\n")
    command << "--location"
    command << "--silent"
    command << "--output /dev/null"
    command << "http://app/my-movies/"
    command = command.join(' ')

    puts "Running smoke test.\n\n"
    system(command)
  end
end


