Chef Server on Vagrant
======================

About
-----

Chef 11 Server / Client on Vagrant

Download Project
----------------

`git clone --recursive git@github.com:paulczar/vagrant-chef.git`  

Install Chef Server
-------------------

_first run may be slow as it has to download a large .deb for chef_

    vagrant up chef

* may as well log in and confirm it worked...


    vagrant ssh chef
    knife client list
        chef-validator
        chef-webui
        vagrant

Install Chef Client
-------------------

    vagrant up node1

* may as well log in and confirm it worked...


    vagrant ssh node1
    knife client list
        chef-validator
        chef-webui
        vagrant

Cookbooks, Roles, etc
---------------------

put cookbooks in - chef-cookbooks/cookbooks
put environments in - chef-cookbooks/environments
put nodes in - chef-cookbooks/nodes
put roles in - chef-cookbooks/roles

Ruby Gems
---------

We're utilizing the embedded ruby with chef.   to install Gems use

/opt/chef[-server]/embedded/bin/gem install berkshelf

to run them 

/opt/chef[-server]/embedded/bin/berks


License and Author
==================

Author:: Paul Czarkowski ( paul@paulcz.net )

Copyright 2013, Paul Czarkowski

Licensed under the Apache License, Version 2.0 (the "License"); you may not use this file except in compliance with the License. You may obtain a copy of the License at

`http://www.apache.org/licenses/LICENSE-2.0`

Unless required by applicable law or agreed to in writing, software distributed under the License is distributed on an "AS IS" BASIS, WITHOUT WARRANTIES OR CONDITIONS OF ANY KIND, either express or implied. See the License for the specific language governing permissions and limitations under the License.
