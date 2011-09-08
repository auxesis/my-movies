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

