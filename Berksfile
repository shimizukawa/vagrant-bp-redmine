#!/usr/bin/env ruby

site :opscode

####################################################################
# community cookbooks (released)

cookbook 'apt'
cookbook 'git'
cookbook 'mercurial'
cookbook 'mysql'
cookbook 'unicorn'


####################################################################
# community cookbooks (unreleased)


####################################################################
# non community cookbooks

# setup mercurial environment files
cookbook 'mercurial-env',
  :git => 'https://github.com/shimizukawa/chef-mercurial-env'

# there was a reason to get from fnichol's github... I forgot.
cookbook "rvm",
  :git => 'https://github.com/fnichol/chef-rvm'

# non community
cookbook "rvm-redmine",
  :git => 'https://github.com/shimizukawa/chef-rvm-redmine'

# non community
cookbook "bp-redmine",
  :git => 'https://github.com/shimizukawa/chef-bp-redmine'

####################################################################
# my bundle cookbooks

