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

namespace :deploy do
  task :symlink do
    run "#{sudo} ln -sf #{current_path} #{current_path}/#{application}"
  end
end
