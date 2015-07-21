# This is a Vagrant configuration to generate a GraphDb-Neo4j VirtualBox image
#
# Tools used:
# - Neo4j Graph DB https://registry.hub.docker.com/u/kbastani/docker-neo4j/
#
# Copyright (c) 2015 Spudmash Media Pty Ltd
#
# GraphDb-Neo4j is made available under the MIT license.
# <http://opensource.org/licenses/MIT>
#

Vagrant.configure(2) do |config|

  config.vm.box = "ubuntu/trusty64"
  config.vm.hostname = "graphdb-neo4j"

  #
  # NAT ports for HOST
  #
  # ::PORTS::
  # - 7474: Neo4j graph db
  #
  config.vm.network "forwarded_port", guest: 7474, host: 7474
  config.vm.network "private_network", ip: "10.0.43.101"
  config.vm.synced_folder "src/", "/home/vagrant/src", :owner => "vagrant", :group => "vagrant"

   config.vm.provider "virtualbox" do |vb|
     vb.gui = false
     vb.cpus = 1
     vb.memory = 1024
   end


   #
   # SHELL: Git clone scripts
   #
   config.vm.provision :shell, path: "bootstrap.sh"

   #
   # DOCKER: Setup Neo4j https://registry.hub.docker.com/u/kbastani/docker-neo4j/
   #
   config.vm.provision "docker" do |d|
     #pull in apache webserver image
     d.pull_images "kbastani/docker-neo4j"

     #
     # app is mapped to 7474 -> expose to host with port 7474
     # + run as daemon
     #
     d.run "graphdb",
       image: "kbastani/docker-neo4j",
       args: "-d -p 7474:7474 -v /Users/vagrant/path/to/neo4j/data:/opt/data",
       daemonize: true

   end
end
